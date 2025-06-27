# Inventory-Item-System

Modüler Unity envanter ve eşya sistemi. Bu repository, OnlineRPG projesinden çıkarılmış envanter, eşya yönetimi ve ekipman sistemlerini içerir.

## 📋 İçerik

### Scripts/Inventory/
- **InventoryItem.cs** - Envanter eşya sınıfı
- **InventoryManager.cs** - Ana envanter yönetici sınıfı
- **InventorySlotUI.cs** - Envanter slot kullanıcı arayüzü
- **SlotType.cs** - Slot türleri enum'u

### Scripts/Equipment/
- **EquipmentManager.cs** - Ekipman yönetici sınıfı

### Scripts/Items/
- **ItemData.cs** - Eşya veri scriptable object'i
- **ItemDatabase.cs** - Eşya veritabanı yöneticisi
- **ItemDatabaseInitializer.cs** - Veritabanı başlatıcı

## 🚀 Kurulum

1. Unity projenize `Scripts` klasörünü kopyalayın
2. Gerekli UI bileşenlerini ve prefab'larını ayarlayın
3. ItemData scriptable object'lerini oluşturun

## 🔗 Bağımlılıklar

- Unity 2022.3 LTS veya üzeri
- TextMeshPro
- Unity UI

## 📝 Notlar

Bu sistem modüler olarak tasarlanmıştır ve diğer Unity projelerine entegre edilebilir. Orijinal OnlineRPG projesi ile bağımsız olarak çalışır.

## 📧 İletişim

Bu sistem ile ilgili sorularınız için issue açabilirsiniz.
