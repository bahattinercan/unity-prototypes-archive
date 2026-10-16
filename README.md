<div align="center">

# Unity Prototip Arşivi

**2022–2023 arasında Unity/C# ile yazılmış 23 oynanabilir prototip.**
Her biri tek bir oynanış fikrini baştan sona çalıştırır: üretim, ilerleme, kayıt, kaybetme.

<sub>Prototiplerin kaynak repoları salt-okunur arşivde; bu repo onların indeksidir.
Amaç 23 ayrı repo yerine tek bir okunabilir anlatı bırakmak.</sub>

</div>

---

## Bu ne, ne değil

**Ne:** Her prototip **çalışan bir oyun döngüsüne** sahipti — başla, oyna, skor al, bitir, kaydet.
Ortak ihtiyaçlar (üretim, kalıcılık, girdi, kamera) her projede tekrar tekrar çözüldü.

**Ne değil:** Ürün değil. Hiçbirinde test yok, mağaza çıkışı yok, performans bütçesi çıkarılmamış.
Bittiği gün donan prototipler — o dönem amaç oynanışı hızlı doğrulamaktı.

---

## Prototipler

### Hiper-casual ve runner

| Prototip | Ne yapıyor | Öne çıkan sistemler |
|---|---|---|
| [`stack-box`](https://github.com/bahattinercan/stack-box) | Üst üste kutu dizme: doğru anda dokun, kuleyi büyüt; blok kaçarsa oyun biter. | `TheStack` ile dizme, skor animasyon kurgusu, tek dokunuş girdi |
| [`beauty-saloon-fever`](https://github.com/bahattinercan/beauty-saloon-fever) | Kaynak toplayıp inşaat ve yükseltme istasyonlarına harcadığın hiper-casual koşu. | `StackManager` + `StackSpawner`/`StackGetter`/`StackGiver` (yığın taşıma), `PayForBuild` + `Upgrade` (harcama ekonomisi) |
| [`crazy-cube`](https://github.com/bahattinercan/crazy-cube) | Prosedürel üretilen platformlarda ilerleyen sonsuz zıplama oyunu; iki butonla kontrol. | `PlatformSpawner`, `PlayerBounds` ile sınır kontrolü, `TapEffect`, kaydırmalı arka plan |
| [`cube-mountain`](https://github.com/bahattinercan/cube-mountain) | Yol boyunca küp toplayıp çizgi hâlinde dizdiğin, elmas çarpanlı engellerden kaçındığın runner. | `LineGenerator` + `DrawLine` (dizilen küp izi), `Collector`, `GemMultiplierObstacle`, yüzde bazlı seviye tamamlama |
| [`climb-the-stair`](https://github.com/bahattinercan/climb-the-stair) | Prosedürel üretilen merdivenlerden sonsuz tırmanma; renk ilerlemesi. | `StairSpawner`/`StairStep`/`StairNewel`, `SmoothCameraFollow`, `DataPersistenceManager` ile ilerleme kaydı |
| [`shot-merger`](https://github.com/bahattinercan/shot-merger) | Namludan çıkan mermileri birleştirerek ilerlediğin nişancı koşusu. | `BulletSpawner`, `CubeCut` (küp kesme), `Barrel`, mobil joystick katmanı |
| [`crush-it`](https://github.com/bahattinercan/crush-it) | Hem oyuncunun hem düşmanın yetenek ve can sistemi olduğu aksiyon koşusu. | `PlayerSkillController` + `EnemySkillController`, `EnemyHealth`, `PickupSpawner`, `ExplosiveObstacle` |

### Arcade ve spor

| Prototip | Ne yapıyor | Öne çıkan sistemler |
|---|---|---|
| [`basketball-master`](https://github.com/bahattinercan/basketball-master) | Joystick ile kontrol edilen 3B basketbol. | `BasketballController` (fizik + atış), üç joystick modu (`Fixed`/`Floating`/`Dynamic`), `CameraFollow` |
| [`basket-time`](https://github.com/bahattinercan/basket-time) | Topu çekip bırakarak attığın 2B basketbol; yörünge önizlemesi. | `DragNShoot` + `TrajectoryLine` (yörünge çizimi), `BasketTrigger` ile skor tespiti, yıldız değerlendirmesi |
| [`run-and-avoid`](https://github.com/bahattinercan/run-and-avoid) | Hareketli engellerden kaçıp altın topladığın 3B koşu. | `ObstacleMovement`, `ForceApplier`, `ColorSelector`, `ModelViewControls` |

### Platform ve aksiyon-macera

| Prototip | Ne yapıyor | Öne çıkan sistemler |
|---|---|---|
| [`2d-platformer`](https://github.com/bahattinercan/2d-platformer) | Hazır bir 2B platform şablonu (Prototype Hero) üzerine kurulmuş; bölüm, kayıt noktası, düşman ve menü ile uçtan uca oynanabilir hâle getirilmiş platform oyunu. | `PlayerController` + `GrabableLedge` (çıkıntı tutma), `MovingPlatform`, `CheckPointController`, `StompBox` (düşman ezme), `LevelManager` |
| [`mario-clone`](https://github.com/bahattinercan/mario-clone) | Mario tarzı 2B platform: farklı düşmanlar, boss ve ateşli saldırı. | `Boss4Health` (fazlı boss), `PlayerShoot` + `FireBullet`, `PlayerDamage`, kurbağa/salyangoz/örümcek davranışları |
| [`zelda-like`](https://github.com/bahattinercan/zelda-like) | Oda oda ilerleyen tepeden bakış aksiyon-macera. | `Inventory` + `Item`, `PowerUp`, `HeartManager`, `Knockback`, `Interactable` + `ContextClue` (etkileşim ipucu), `RoomMove` kamera geçişi, devriye düşmanı (`PatrolLog`) |

### Bulmaca ve kelime

| Prototip | Ne yapıyor | Öne çıkan sistemler |
|---|---|---|
| [`candy-explosion`](https://github.com/bahattinercan/candy-explosion) | Hedef tabanlı match-3: eşleştir, hedefi tamamla, tıkandığında ipucu al. | `FindMatches` + `Board`/`Dot` (grid motoru), `GoalManager`, `HintManager`, `CandySO` ile veri odaklı şeker tanımları, `DataPersistenceManager` ile kayıt |
| [`match_2_blast`](https://github.com/bahattinercan/match_2_blast) | Blok patlatma bulmacası; seviyeler ve görevler veri dosyalarından geliyor. | `GameGrid` + `GameLogic` (grid çekirdeği), `Quest`/`QuestPanel`, `BlackBomb`, `LevelSO`/`LevelListSO`, `InvalidGridException` ile doğrulama |
| [`word-of-the-war`](https://github.com/bahattinercan/word-of-the-war) | Harfleri klavyeden sürükleyip kelime kurarak düşmanla savaştığın kelime oyunu. | `KeyboardDragHandler` + `KeyboardController`, `WordController` + `WordLists`, `HealthController` |

### Ritim

| Prototip | Ne yapıyor | Öne çıkan sistemler |
|---|---|---|
| [`rhythm-surfer`](https://github.com/bahattinercan/rhythm-surfer) | Engelleri doğru renkle karşılayarak geçtiğin ritim oyunu. | `AudioPeer` (FFT ile bant analizi), `ChangeColorObs` (renk değiştiren engel), `CristalSpawner`, `PlayerColor`, `HpPanel` |
| [`catch-rhythm`](https://github.com/bahattinercan/catch-rhythm) | `rhythm-surfer` ile aynı çekirdeği paylaşan devam prototipi: ritim + şekil/renk eşleştirme, oynanış ayarları ve ilerleme kaydı. | `AudioClipSO`/`MaterialsSO`/`ColorListSO` ile veri odaklı içerik, `CristalButtonUI`, `GameplaySettingsSO`, `DataPersistenceManager` |

### Strateji ve savunma

| Prototip | Ne yapıyor | Öne çıkan sistemler |
|---|---|---|
| [`protect-base`](https://github.com/bahattinercan/protect-base) | Üs savunma: bina kur, onar, gece-gündüz döngüsünde dalgaları püskürt. | `BuildingConstruction` + `BuildingGhost` (ızgara üzerinde yerleştirme önizlemesi), `BuildingTypeSO` ile veri odaklı bina tipleri, `EnemyWaveManager` + `EnemyWaveUI`, `DayNightCycle`, `CinemachineShake`, `ConstructionTimerUI` |

### Idle ve simülasyon

| Prototip | Ne yapıyor | Öne çıkan sistemler |
|---|---|---|
| [`plant-a-tree`](https://github.com/bahattinercan/plant-a-tree) | Ağaç yetiştirme idle oyunu; reklam ödülüyle hızlandırma. | `Consumer` + `DataCarrier` (üretim-tüketim döngüsü), `EarthColorChanger` + `EarthSpinScript` (gezegen ilerlemesi), AdMob entegrasyonu (`AdBanner`, `AdInterstitial`, `AdRewarded`) |

### VR ve deneysel

| Prototip | Ne yapıyor | Öne çıkan sistemler |
|---|---|---|
| [`math-vr`](https://github.com/bahattinercan/math-vr) | Cardboard/Daydream için VR matematik etkileşimi. | Google VR SDK üzerine kurulu; kendi tarafımda olay sistemi (`BoolEvent`, `FloatEvent`, `ButtonEvent`) ve `Grab` ile tutma etkileşimi |
| [`audio-virtualization`](https://github.com/bahattinercan/audio-virtualization) | Müzikten sürülen 3B görselleştirme: 512 küp ve ışıklar sesle hareket eder. | `AudioPeer` (FFT bant verisi), `ParamCube` + `Instatiate512Cubes` ile örnekleme, `LightOnAudio` |

### Araç

| Prototip | Ne yapıyor | Öne çıkan sistemler |
|---|---|---|
| [`spawning-system`](https://github.com/bahattinercan/spawning-system) | Unity için yeniden kullanılabilir spawn sistemi (oyun değil, paket). | Tek sorumluluğa sahip `SpawningSystem` bileşeni; projeden bağımsız kullanılabilir |

---

## 23 prototipte tekrar eden sistemler

Ayrı ayrı bakınca küçük görünen işler, toplu bakınca aynı mühendislik alışkanlığını gösteriyor:

| Desen | Nerede karşımıza çıkıyor |
|---|---|
| **Üretim yönetimi** | `PlatformSpawner`, `StairSpawner`, `BulletSpawner`, `PickupSpawner`, `CristalSpawner`, `StackSpawner`, `EnemyWaveManager` |
| **Veri odaklı içerik** (ScriptableObject) | `BuildingTypeSO`, `CandySO`, `LevelSO`/`LevelListSO`, `AudioClipSO`, `ColorListSO`, `MaterialsSO`, `GameplaySettingsSO` |
| **Kalıcılık katmanı** | Aynı şablon tekrar tekrar: `DataPersistenceManager` + `FileDataHandler` + `IDataPersistence` (7 prototipte) |
| **Mobil girdi soyutlaması** | `FixedJoystick` / `FloatingJoystick` / `DynamicJoystick` üçlüsü + `MobileInput` |
| **Durum makineleri** | `EGameState`, `EPlayerState`, `EObstacle`, `EColor`, `EShape`, `EDotType` enum'ları ve geçişleri |
| **Kamera davranışları** | `SmoothCameraFollow`, `CameraFollow`, `CameraMinMaxPos`, `CinemachineShake` |

---

## Bugün aynısını yazsam

Bu bölümü arşivin parçası sayıyorum; 2022'deki hâlimle 2026'daki hâlim arasındaki fark burada:

- **Test yoktu.** Skor, ekonomi ve eşleşme mantığı sahnede MonoBehaviour içindeydi.
  Bugün `match_2_blast`'taki `GameLogic` gibi saf C# çekirdekleri ayırıp JVM/NUnit testiyle kilitlerdim.
- **Dengeleme değerleri prefab'lara dağılmıştı.** Tamamı tek ScriptableObject ayar dosyasına toplanmalı
  — `GameplaySettingsSO`'yu tek prototipte denedim, hepsine yaymadım.
- **README yazmadım.** Sonuç: 24 repo yıllarca isimsiz kaldı ve 2026'da ne olduklarını çıkarmak için
  script adlarını tek tek okumam gerekti. Bu repo tam olarak o borcun ödemesi.
- **Kayıt sistemi her projede yeniden yazıldı.** Tek pakete çıkarılıp paylaşılmalıydı.
- **Bileşenler prefab hiyerarşisine sıkı bağlıydı.** Arayüz üzerinden enjekte edip düzenlenebilir kılardım.

---

<div align="center">

**Kaynak repolar salt-okunur arşivde, kodu okumak için hâlâ açık.**
Profil ve diğer işler: [github.com/bahattinercan](https://github.com/bahattinercan)

</div>
