---
title: 'MPI ile Dağıtık Sistemlerde Dinamik Yük Dengeleme: MD5 Kırıcı Projesi'
description: 'C++ ve MPI kullanarak, dağıtık bellek mimarisinde asenkron haberleşme ve dinamik yük dengeleme teknikleriyle brute-force simülasyonu.'
pubDate: 2026-07-16
---

<div style="display: inline-flex; align-items: center; gap: 10px; background: #f5f2eb; color: #597a61; padding: 8px 16px; border-radius: 30px; font-weight: 600; font-size: 0.9em; margin-bottom: 1.5rem; border: 1px solid #e6e0d6; box-shadow: 0 4px 12px rgba(89, 122, 97, 0.08);">
  <span style="width: 10px; height: 10px; background-color: #3b82f6; border-radius: 50%; box-shadow: 0 0 8px #3b82f6;"></span>
  🚀 Paralel programlama mimarileri üzerinde başarıyla test edilmiştir.
</div>

## 🎯 Projenin Çıkış Noktası ve Amacı

Bu proje, **Paralel Programlama** dersindeki teorik bilgileri (MPI, süreçler arası haberleşme, hızlandırma analizi) pratik bir laboratuvar ortamına dökmek amacıyla geliştirilmiştir. Geleneksel sabit veri dağıtımı yerine, sistem kaynaklarını en verimli şekilde kullanan **Master-Worker (Usta-İşçi)** mimarisi kurgulanmıştır.

> 💡 **Geliştirme Notu:** Şifre kırma (brute-force) senaryosu, yüksek başarımlı hesaplama (HPC) dünyasında "utanç verici derecede paralel" (embarrassingly parallel) problemlerin en iyi test yatağıdır. Proje; mesajlaşma maliyetini, `MPI_ANY_SOURCE` ile asenkron yönetimi ve ölçeklenebilirlik kavramlarını deneyimlemek için tasarlanmıştır.

---

## ⚙️ Teknik Mimarisi ve İletişim Protokolü

Sistem, Master sürecin işçi süreçleri yönettiği tamamen dinamik bir yapıya sahiptir:

* **İletişim Katmanı:** `MPI` (Message Passing Interface) üzerinde özel tanımlı etiketler (`TAG_WORK_REQUEST`, `TAG_WORK_DATA`, `TAG_RESULT_FOUND`).
* **Yük Dengeleme:** Master süreç, işçilerden gelen taleplere göre `chunk_size` (blok boyutu) bazlı görev ataması yapar.
* **Senkronizasyon:** `MPI_Iprobe` ve `MPI_ANY_SOURCE` kullanımıyla kilitlenme (deadlock) yaşamayan, asenkron haberleşme protokolü.
* **Hızlandırma Analizi:** Amdahl Kanunu baz alınarak, süreç sayısı arttıkça elde edilen teorik ve gerçek hızlandırma karşılaştırması.



---

## 🛠️ Kullanılan Teknolojiler

* **Diller:** C++, Bash (Test süreçleri için)
* **Kütüphaneler:** OpenMPI, Frank Thilo MD5 Library
* **Platform:** Kali Linux, VirtualBox, Linux Kernel Network Stack

---

<div class="project-links">
  <a href="https://github.com/6usraatik/Parallel-MPI-BruteForce" target="_blank" class="github-btn">
    🐙 GitHub Deposu ➔
  </a>
</div>