# Inventory-Item-System

🎮 **Unity için Gelişmiş Modüler Envanter Sistemi**

Bu repository, multiplayer OnlineRPG projesinden çıkarılmış, tam özellikli ve modüler bir envanter-eşya yönetim ## 📈 İstatistikler

- **📁 Toplam Script Dosyası**: 10
- **💻 Toplam Kod Satırı**: 4400+
- **🎮 Desteklenen Unity Sürümü**: 2022.3 LTS+
- **🌐 Network**: Photon PUN2
- **🏗️ Architecture**: Modular Design Pattern
- **📱 Platform**: PC, Mobile Ready
- **🔄 Son Güncelleme**: 27 Haziran 2025

## 📞 İletişim

- **👨‍💻 GitHub**: [@grknsytrk](https://github.com/grknsytrk)
- **📧 Email**: oyungrkn@gmail.com
- **🐛 Bug Reports**: GitHub Issues kullanın
- **💡 Feature Requests**: GitHub Discussions kullanın

Bu sistem ile ilgili sorularınız için issue açabilir veya email atabilirsiniz.idir. Photon PUN2 ağ desteği, ScriptableObject tabanlı veri yönetimi ve esnek UI sistemi ile Unity projelerinize kolayca entegre edilebilir.

## 🌟 Özellikler

- 🔄 **Multiplayer Desteği**: Photon PUN2 ile senkronize envanter sistemi
- 📦 **ScriptableObject Tabanlı**: Esnek ve genişletilebilir eşya veri sistemi
- 🎨 **Modüler UI**: Drag & Drop destekli kullanıcı dostu arayüz
- ⚡ **Performans Optimizasyonu**: Efficient slot management ve memory optimization
- 🔧 **Kolay Entegrasyon**: Plug-and-play modüler yapı
- 📊 **Veritabanı Sistemi**: Merkezi eşya yönetimi ve ID tabanlı referanslama

## 📋 İçerik

### Scripts/Inventory/
- **InventoryItem.cs** - Envanter içindeki eşya sınıfı. Eşya miktarı, ID ve stackleme özelliklerini yönetir
- **InventoryManager.cs** - Ana envanter yönetici sınıfı. Multiplayer senkronizasyon, slot yönetimi ve UI kontrolü
- **InventorySlotUI.cs** - Envanter slot kullanıcı arayüzü. Drag&Drop, tooltip ve görsel güncellemeler
- **SlotType.cs** - Slot türleri enum'u. Farklı eşya tiplerinin kategorize edilmesi için

### Scripts/Equipment/
- **EquipmentManager.cs** - Ekipman yönetici sınıfı. Karakter stat bonusları, ekipman slotları ve multiplayer senkronizasyon

### Scripts/Items/
- **ItemData.cs** - Eşya veri scriptable object'i. Eşya özelliklerini, ikonları ve stat bonuslarını tutar
- **ItemDatabase.cs** - Eşya veritabanı yöneticisi. Singleton pattern ile merkezi eşya erişimi
- **ItemDatabaseInitializer.cs** - Veritabanı başlatıcı. Oyun başlangıcında tüm eşyaları yükler

## 🧠 Sistem Mantığı

### 📦 Envanter Sistemi
- **Slot Tabanlı**: Her slot bir eşya türü tutabilir ve stackleme destekler
- **ID Sistemi**: Her eşya benzersiz string ID ile tanımlanır
- **Multiplayer**: Photon PUN2 RPC'leri ile tüm oyuncularda senkronize
- **Performans**: Object pooling ve efficient UI güncellemeleri

### 🎯 Eşya Sistemi  
- **ScriptableObject**: Eşya verileri asset olarak saklanır, runtime'da değişmez
- **Database Pattern**: Merkezi erişim için singleton ItemDatabase
- **Type Safety**: Enum'lar ile tip güvenliği
- **Extensible**: Yeni eşya türleri kolayca eklenebilir

### ⚙️ Ekipman Sistemi
- **Stat Bonusları**: Ekiplenen eşyalar karakter statlarını etkiler  
- **Slot Kısıtları**: Her ekipman tipi belirli slotlara yerleştirilebilir
- **Visual Updates**: Karakter modeli ekipmana göre güncellenir
- **Network Sync**: Tüm oyuncular ekipman değişikliklerini görür

## 🚀 Kurulum

### 1. Dosyaları Projenize Ekleyin
```bash
# Repository'yi klonlayın
git clone https://github.com/grknsytrk/Inventory-Item-System.git

# Veya Scripts klasörünü Unity projenize kopyalayın
```

### 2. Bağımlılıkları Kurun
- **Photon PUN2**: Asset Store'dan indirin (Multiplayer için gerekli)

### 3. Temel Kurulum
```csharp
// ItemDatabase'i sahneye ekleyin
GameObject dbObject = new GameObject("ItemDatabase");
dbObject.AddComponent<ItemDatabase>();
dbObject.AddComponent<ItemDatabaseInitializer>();

// Envanter UI'ını kurduğunuzda InventoryManager'i ekleyin
Canvas inventoryCanvas = FindObjectOfType<Canvas>();
inventoryCanvas.gameObject.AddComponent<InventoryManager>();
```

### 4. Eşya Oluşturma
- **Assets** klasöründe sağ tık > **Create > Item Data**
- Eşya özelliklerini düzenleyin (İsim, İkon, Stats, vb.)
- ItemDatabase'e eşyayı kaydedin

## 🔧 Teknolojiler & Mimariler

### 🏗️ Design Patterns
- **Singleton Pattern**: ItemDatabase için merkezi erişim
- **Observer Pattern**: UI güncellemeleri için event system
- **Factory Pattern**: Eşya instantiation için
- **Command Pattern**: Undo/Redo işlemleri için

### 🌐 Networking (Photon PUN2)
```csharp
// RPC ile envanter senkronizasyonu
[PunRPC]
void SyncInventoryItem(string itemId, int quantity, int slotIndex)
{
    // Tüm oyuncularda envanter güncellenir
}
```

### 📊 Data Management
- **ScriptableObject**: Runtime'da değişmeyen eşya verileri
- **JSON Serialization**: Save/Load işlemleri
- **Event-Driven Architecture**: Loose coupling için

## 🔗 Bağımlılıklar

### Unity Packages
- **Unity 2022.3 LTS** veya üzeri
- **TextMeshPro** (UI text rendering için)
- **Unity UI** (Canvas ve UI bileşenleri için)

### Third-Party Assets  
- **Photon PUN2** (Multiplayer networking için)
- **DOTween** (UI animasyonları için - opsiyonel)

### System Requirements
- **.NET Framework 4.7.1** veya üzeri
- **C# 8.0** language features

## 💡 Kullanım Örnekleri

### Eşya Ekleme
```csharp
// ID ile eşya ekleme
InventoryManager.Instance.AddItem("sword_001", 1);

// ItemData ile eşya ekleme  
ItemData newItem = ItemDatabase.Instance.GetItemById("potion_healing");
InventoryManager.Instance.AddItem(newItem, 5);
```

### Eşya Kontrolü
```csharp
// Envanterde eşya var mı?
bool hasItem = InventoryManager.Instance.HasItem("key_dungeon");

// Eşya miktarını öğren
int itemCount = InventoryManager.Instance.GetItemCount("gold_coin");
```

### Event Listening
```csharp
// Envanter değişikliklerini dinle
InventoryManager.OnInventoryChanged += OnInventoryUpdated;

void OnInventoryUpdated(InventoryItem item, int slotIndex)
{
    Debug.Log($"Slot {slotIndex}'de {item.ItemId} güncellendi");
}
```

## 🎯 Özellik Detayları

### 📦 Envanter Sistemi Özellikleri
- **Dinamik Slot Sistemi**: İstediğiniz kadar slot ekleyebilirsiniz
- **Stackable Items**: Aynı eşyalar otomatik olarak birleşir
- **Drag & Drop**: Sürükle-bırak ile eşya taşıma
- **Tooltip System**: Fare ile eşya üzerine gelince detaylar
- **Filtering**: Eşya türlerine göre filtreleme
- **Search Function**: İsim ile eşya arama

### ⚔️ Ekipman Sistemi Özellikleri  
- **Equipment Slots**: Kask, Zırh, Silah, Ayakkabı vb.
- **Stat Bonuses**: STR, DEF, HP, MP bonusları
- **Visual Equipment**: Karakterde görsel değişiklik
- **Set Bonuses**: Takım bonusları (gelecek güncelleme)
- **Durability System**: Eşya dayanıklılığı (gelecek güncelleme)

### 🔄 Multiplayer Özellikleri
- **Real-time Sync**: Anlık envanter senkronizasyonu  
- **Trade System**: Oyuncular arası eşya ticareti (gelecek güncelleme)
- **Loot Distribution**: Grup içi ganimet paylaşımı
- **Anti-Cheat**: Server-side validation (gelecek güncelleme)

## � Gelecek Güncellemeler

- [ ] **Trading System** - Oyuncular arası ticaret
- [ ] **Set Equipment Bonuses** - Takım bonusları  
- [ ] **Durability System** - Eşya dayanıklılığı
- [ ] **Enchantment System** - Eşya geliştirme
- [ ] **Bank System** - Depo sistemi
- [ ] **Mobile Touch Support** - Mobil cihaz desteği

## 📝 Notlar

Bu sistem modüler olarak tasarlanmıştır ve diğer Unity projelerine entegre edilebilir. Orijinal OnlineRPG projesi ile bağımsız olarak çalışır.

### Performans Optimizasyonları
- **Object Pooling**: UI elementleri için memory optimization
- **Event Batching**: Toplu UI güncellemeleri  
- **Lazy Loading**: İhtiyaç halinde eşya yükleme
- **Memory Management**: Automatic garbage collection optimization

Bu sistem ile ilgili sorularınız için issue açabilirsiniz.
