Kritik Güvenlik Zafiyeti: Parts Catalogs API key'imiz frontend tarafında (Network sekmesinde) ifşa oluyor. Bu durumu çözmek için backend'de bir proxy (aracı) mekanizması kurmalıyız.

Dış API'ye ait gizli anahtarı (API_KEY) sadece backend'in .env dosyasında tut ve kod içinde process.env üzerinden çağır.

/api/catalog/search-vin/:vin endpoint'ini (şasi sorgulama controller'ını) güncelle. Frontend artık doğrudan dışarıya değil, sana (bu endpoint'e) istek atacak.

Bu controller, frontend'den şasi numarasını (vin) alsın, backend sunucusu üzerinden (sunucudan sunucuya) api.parts-catalogs.com adresine kendi gizli API key'ini kullanarak istek atsın.

Dış API'den gelen veriyi alıp frontend'e temiz bir JSON olarak (başarılıysa data, başarısızsa hata mesajı) döndür.