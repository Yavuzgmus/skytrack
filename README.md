# SkyTrack

Drone görüntüsünden kavşaktaki araçları gerçek zamanlı tespit eden, takip eden ve trafik analitiği üreten C++ tabanlı bir sistem.

> **Durum:** Geliştirme aşamasında — Faz 0 (hazırlık ve ortam). Ayrıntılı plan için [docs/ROADMAP.md](docs/ROADMAP.md).

## Planlanan bileşenler

| Bileşen | Teknoloji | Görevi |
| --- | --- | --- |
| `engine/` | C++17, OpenCV, ONNX Runtime, LibTorch | Tespit, çoklu nesne takibi (ByteTrack), trafik analitiği |
| `training/` | Python, LibTorch | YOLO fine-tune, sıfırdan CNN, veri hazırlama |
| `api/` | ASP.NET Core, SignalR, PostgreSQL | Veri alımı, sorgular, canlı yayın |
| `web/` | React, Vite, TypeScript | Canlı izleme ve analitik dashboard |
| `docker/` | Docker, Docker Compose | Tek komutla kurulum |

## Repo yapısı

```
skytrack/
├── engine/      # C++ çıkarım motoru
├── training/    # Model eğitimi ve veri hazırlama
├── api/         # ASP.NET Core Web API
├── web/         # React dashboard
├── configs/     # Çalışma ve bölge yapılandırmaları
├── docker/      # Dockerfile'lar
├── docs/        # Roadmap, mimari karar kayıtları (ADR)
└── .github/     # CI workflow'ları
```

## Geliştirme ortamı

Proje Windows 11 üzerinde WSL2 + Ubuntu 24.04 ile geliştiriliyor. Kullanılan araç sürümleri:

| Araç | Sürüm |
| --- | --- |
| g++ | 13.3.0 |
| CMake | 3.28.3 |
| Ninja | 1.11.1 |
| gdb | 15.1 |
| clang-format | 18.1.3 |
| Git | 2.43.0 |

## Teşekkürler

- İlham kaynağı: [selorito/vehicle-detection-cpp](https://github.com/selorito/vehicle-detection-cpp)
- Veri setleri: [UAVDT](https://arxiv.org/abs/1804.00518), [VisDrone](https://github.com/VisDrone/VisDrone-Dataset)

## Lisans

Kod [MIT lisansı](LICENSE) ile yayınlanır. Veri setleri kendi lisanslarına tabidir (VisDrone yalnızca ticari olmayan araştırma kullanımı içindir) ve bu repoya dahil değildir.
