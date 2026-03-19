# Rizo_Arias-post2-u4
# Posts Offline-First - Post-Contenido 2 (Unidad 4)

Aplicación Android con **arquitectura offline-first** usando Room + Retrofit + TTL (5 minutos) + WorkManager para sincronización de favoritos.


## 📸 Evidencias (5 capturas requeridas)

| Captura                        | Descripción |
|--------------------------------|-----------|
| [captura_posts_offline.png](evidencias/captura_posts_offline.png) | App funcionando sin red (datos desde Room) |
| [captura_ttl_logcat.png](evidencias/captura_ttl_logcat.png) | Logcat mostrando que NO se llama a la red dentro del TTL |
| [captura_pending_sync.png](evidencias/captura_pending_sync.png) | Database Inspector con estado "PENDING_SYNC" |
| [captura_synced.png](evidencias/captura_synced.png) | Database Inspector después de la sincronización ("SYNCED") |
| [captura_workmanager_success.png](evidencias/captura_workmanager_success.png) | Log de WorkManager mostrando SUCCESS |

## 🛠️ Arquitectura implementada
- **Offline-first**: UI siempre observa Room (Flow + StateFlow)
- **Caching con TTL**: 5 minutos (refreshIfStale)
- **Favoritos offline**: toggle local + syncStatus = "PENDING_SYNC"
- **Sincronización**: WorkManager con red requerida + reintentos
- **Fuente única de verdad**: Repository

