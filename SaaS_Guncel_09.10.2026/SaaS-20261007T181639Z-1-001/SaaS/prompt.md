"Bayi frontend'i oturum açmış kullanıcının güncel bilgilerini çekerken (/api/auth/me veya ilgili profil endpoint'i), onay durumu (Tenant status) eski/hatalı geliyor olabilir.

/api/auth/me (veya ilgili profil getirme) controller'ını kontrol et. Bu endpoint çalıştırıldığında veritabanından (Prisma) Tenant tablosuna include veya join ile anlık sorgu atarak güncel status (veya isActive) bilgisini alıp JSON yanıtına eklediğinden emin ol.

Giriş yapıldığında oluşturulan JWT Token payload'unun içine statik statü bilgisi gömme; statü kontrollerini her zaman veritabanından anlık (real-time) olarak çekerek doğrula."