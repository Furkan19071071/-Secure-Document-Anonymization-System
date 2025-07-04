# 📚 Akademik Makale Yönetim Sistemi

> Akademik makalelerin değerlendirilmesi için kapsamlı bir yönetim sistemi. Yazarlar, editörler ve hakemler için ayrı paneller sunar.

## 🚀 Özellikler

### 👥 Çok Rollu Kullanıcı Sistemi
- **Yazarlar**: Makale yükleme, durum takibi, revizyon gönderimi
- **Editörler**: Makale yönetimi, hakem ataması, değerlendirme süreçleri
- **Hakemler**: Makale değerlendirme, puan verme, yorum yapma

### 📄 Makale İşleme
- PDF dosya yükleme ve indirme
- Otomatik makale anonimleştirme
- Makale takip numarası sistemi
- Revizyon yönetimi

### 🔐 Güvenlik
- JWT tabanlı kimlik doğrulama
- Rol tabanlı erişim kontrolü
- Güvenli dosya yükleme
- Veri şifreleme

### 📊 Yönetim Paneli
- Makale durumu takibi
- Hakem atama sistemi
- Mesajlaşma sistemi
- Değerlendirme raporları

## 🛠️ Teknolojiler

### Backend
- **Node.js** + **Express.js** - REST API sunucusu
- **MySQL** + **Sequelize** - Veritabanı ve ORM
- **JWT** - Kimlik doğrulama
- **Multer** - Dosya yükleme
- **PDF-lib** - PDF işleme
- **bcryptjs** - Şifre hashleme

### Frontend
- **React.js** - Kullanıcı arayüzü
- **React Router** - Sayfa yönlendirme
- **Bootstrap** + **React Bootstrap** - UI bileşenleri
- **Axios** - HTTP istekleri
- **Context API** - Durum yönetimi

### Python Entegrasyonu
- **Python** - PDF anonimleştirme
- **Natural Language Processing** - Metin işleme
- **PDF işleme kütüphaneleri**

## 📋 Ön Koşullar

- **Node.js** (v14 veya üzeri)
- **MySQL** (v5.7 veya üzeri)
- **Python** (v3.8 veya üzeri)
- **npm** veya **yarn**

## 🔧 Kurulum

### 1. Projeyi Klonlayın
```bash
git clone https://github.com/kullanici-adi/makale-yonetim-sistemi.git
cd makale-yonetim-sistemi
```

### 2. Backend Kurulumu

```bash
cd backend
npm install
```

### 3. Veritabanı Konfigürasyonu

`.env` dosyasını oluşturun:
```env
DB_HOST=localhost
DB_USER=root
DB_PASSWORD=şifreniz
DB_NAME=yazlab
DB_DIALECT=mysql
PORT=5000
JWT_SECRET=güvenli-bir-anahtar
```

### 4. Python Ortamını Hazırlayın

```bash
cd backend/python
python create_venv.py
```

### 5. Veritabanını Başlatın

```bash
node resetDb.js
node initDirs.js
```

### 6. Backend Sunucusunu Başlatın

```bash
npm start
```

### 7. Frontend Kurulumu

```bash
cd frontend
npm install
npm start
```

## 🎯 Kullanım

### Makale Yükleme
1. Ana sayfadan "Makale Yükle" seçeneğine tıklayın
2. PDF dosyanızı seçin
3. Makale bilgilerini doldurun
4. Takip numaranızı not alın

### Editör Paneli
1. "Editör Paneli" → "Yönetici" sayfasına gidin
2. Yeni makaleleri görüntüleyin
3. Hakemleri atayın
4. Değerlendirme sürecini takip edin

### Hakem Değerlendirmesi
1. "Hakem Girişi" ile giriş yapın
2. Atanan makaleleri görüntüleyin
3. Değerlendirme formunu doldurun
4. Puan ve yorumlarınızı ekleyin

## 📁 Proje Yapısı

```
📦 makale-yonetim-sistemi/
├── 📁 backend/
│   ├── 📁 config/          # Veritabanı konfigürasyonu
│   ├── 📁 controllers/     # İş mantığı
│   ├── 📁 middleware/      # Kimlik doğrulama
│   ├── 📁 models/          # Veritabanı modelleri
│   ├── 📁 routes/          # API rotaları
│   ├── 📁 python/          # Python scriptleri
│   ├── 📁 uploads/         # Yüklenen dosyalar
│   └── 📄 server.js        # Ana sunucu dosyası
├── 📁 frontend/
│   ├── 📁 public/          # Statik dosyalar
│   ├── 📁 src/
│   │   ├── 📁 components/  # React bileşenleri
│   │   ├── 📁 context/     # Context API
│   │   ├── 📁 hooks/       # Custom hooks
│   │   ├── 📁 pages/       # Sayfa bileşenleri
│   │   ├── 📁 services/    # API servisleri
│   │   └── 📁 utils/       # Yardımcı fonksiyonlar
│   └── 📄 package.json
└── 📄 README.md
```

## 🗄️ Veritabanı Şeması

### Ana Tablolar
- `Users` - Kullanıcı bilgileri
- `Makale` - Makale bilgileri
- `Hakem` - Hakem bilgileri
- `Editor` - Editör bilgileri
- `HakemDegerlendirme` - Değerlendirme kayıtları
- `Mesaj` - Mesajlaşma sistemi
- `UzmanlikAlani` - Uzmanlık alanları

## 🔧 Geliştirme

### Backend Geliştirme

```bash
cd backend
npm run dev  # nodemon ile otomatik yeniden başlatma
```

### Frontend Geliştirme

```bash
cd frontend
npm start  # React development server
```

### Veritabanı Sıfırlama

```bash
cd backend
node resetDb.js
node initDirs.js
```

## 📝 API Dokümantasyonu

### Kimlik Doğrulama
- `POST /api/users/register` - Kullanıcı kaydı
- `POST /api/users/login` - Giriş yapma

### Makale İşlemleri
- `POST /api/makaleler/yukle` - Makale yükleme
- `GET /api/makaleler/durum/:takipNo` - Makale durumu
- `POST /api/makaleler/:id/anonimize` - Makale anonimleştirme

### Hakem İşlemleri
- `POST /api/hakem/makale/:id/degerlendirme` - Değerlendirme yapma
- `GET /api/hakem/makalelerim` - Atanan makaleler

## 🧪 Test

```bash
# Backend testleri
cd backend
npm test

# Frontend testleri
cd frontend
npm test
```

## 🚀 Deployment

### Production Build

```bash
# Frontend build
cd frontend
npm run build

# Backend için PM2 kullanımı
npm install -g pm2
pm2 start server.js --name "makale-sistemi"
```

### Docker ile Deployment

```bash
docker-compose up -d
```

## 🤝 Katkıda Bulunma

1. Bu repo'yu fork edin
2. Feature branch oluşturun (`git checkout -b feature/yeni-ozellik`)
3. Değişikliklerinizi commit edin (`git commit -am 'Yeni özellik eklendi'`)
4. Branch'inizi push edin (`git push origin feature/yeni-ozellik`)
5. Pull Request oluşturun

## 📜 Lisans

Bu proje MIT lisansı altında lisanslanmıştır. Detaylar için `LICENSE` dosyasını inceleyin.

## 📞 İletişim

- **Proje Sahibi**: [Adınız]
- **E-posta**: [email@example.com]
- **LinkedIn**: [LinkedIn Profiliniz]

## 🙏 Teşekkürler

Bu projeyi geliştirirken yardımcı olan tüm açık kaynak kütüphanelere ve topluluklara teşekkürler.

---

⭐ **Bu projeyi beğendiyseniz, lütfen yıldız vermeyi unutmayın!**
