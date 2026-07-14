---
title: 'BashGuard-IPS: Otonom Log Analiz ve Saldırı Engelleme Sistemi'
description: 'Linux ortamında sistem loglarını gerçek zamanlı izleyerek anomali ve kaba kuvvet (brute-force) saldırılarını tespit eden, iptables firewall entegrasyonuyla şüpheli IP leri otonom olarak engelleyen Blue Team odaklı IPS projesi.'
pubDate: 2026-07-14
---

<div style="display: inline-flex; align-items: center; gap: 10px; background: #f5f2eb; color: #597a61; padding: 8px 16px; border-radius: 30px; font-weight: 600; font-size: 0.9em; margin-bottom: 1.5rem; border: 1px solid #e6e0d6; box-shadow: 0 4px 12px rgba(89, 122, 97, 0.08);">
  <span style="width: 10px; height: 10px; background-color: #22c55e; border-radius: 50%; box-shadow: 0 0 8px #22c55e;"></span>
  🛡️ Bu proje başarıyla tamamlanmış ve sistem servisi olarak yayımlanmıştır.
</div>

## 🎯 Projenin Çıkış Noktası ve Amacı

**BashGuard-IPS**, sunucu loglarını sıfır gecikmeyle takip eden, saldırı örüntülerini (regex) algılayan ve eşik değeri aşımında sistemin güvenlik duvarına dinamik kurallar yazarak tehditleri anında bloklayan hafif ve bağımsız bir **Saldırı Engelleme Sistemidir (IPS)**. 

Log okuyucu (sensor), analiz motoru, iptables infaz motoru ve süresi dolan cezaları kaldıran otonom af motoru (reaper) olmak üzere 4 temel katmandan oluşur.

> 💡 **Geliştirme Notu:** Proje, bir Linux sisteminin derinliklerini kavramak amacıyla geliştirildi. Boru hatları (pipeline), asenkron arka plan süreçleri, sinyal yakalama (`trap`) ve systemd servis entegrasyonu sayesinde araç; sunucu yeniden başlasa bile otomatik devreye giren 7/24 aktif bir koruma kalkanına dönüştürüldü.

---

## ⚙️ Planlanan ve Aktif Teknoloji Mimarisi

* **Çekirdek Dil & Betik:** Bash Scripting
* **Ağ Güvenliği & Firewall:** Linux Ağ Yığıtı, `iptables` (İzole Zincir / Custom Chain Yönetimi)
* **Sistem & Servis Yönetimi:** `systemd` Daemon Entegrasyonu, Arka Plan Süreç Yönetimi
* **Platform & Geliştirme Ortamı:** Kali Linux, VirtualBox
* **Sürüm Kontrol & İş Birliği:** Git, GitHub

---

<div class="project-links">
  <a href="https://github.com/6usraatik/bashguard-ips" target="_blank" class="github-btn">
    🐙 GitHub Deposu ➔
  </a>
</div>