<p align="center">
  <img src="icon.png" width="96" alt="ZenTrader" />
</p>

<h1 align="center">ZenTrader</h1>

<p align="center">
  Diario de trading, cuentas y desafíos de prop firm, analítica con AI Coach y coaching automático.<br/>
  Offline-first, con sincronización opcional y sistema de membresías por niveles.
</p>

<p align="center">
  <a href="https://zentrader-preview.vercel.app">🔗 Ver landing / demo interactivo</a>
</p>

> 🔒 **El código fuente de este proyecto es privado.** Este repositorio es una vista general (arquitectura, features, capturas) para portafolio. Código disponible bajo solicitud en una entrevista.

---

## Capturas reales

<p align="center">
  <img src="screenshots/dashboard.jpeg" width="180" />
  <img src="screenshots/ai-coach.jpeg" width="180" />
  <img src="screenshots/equity-curve.jpeg" width="180" />
  <img src="screenshots/confluence.jpeg" width="180" />
  <img src="screenshots/log-trade.jpeg" width="180" />
</p>

## Qué hace

- **Diario de trading**: registro completo (par, entrada, SL/TP, lote, confluencias) o "Quick Log" en segundos.
- **Cuentas y desafíos**: administra múltiples cuentas y sigue reglas de desafíos de prop firm (drawdown, objetivo, días mínimos) en tiempo real.
- **Analítica & AI Coach**: net profit, win rate, curva de equity, heatmap por día, rendimiento por confluencia/par/emoción, ganancia por hora del día, e insights automáticos.
- **Logros**: gamificación para reforzar hábitos de trading saludables.
- **Notas**: diario aparte vinculable a un trade específico.
- **Seguridad**: bloqueo biométrico y autenticación propia contra el backend.
- **Exportación**: reportes a CSV y PDF.
- **Perfil público**: opcional, compartible.
- **Membresías**: 4 niveles (Free / Pro / Elite / Unlimited) con pagos manuales vía Binance Pay y USDT (TRC20), revisados y aprobados por un administrador.

## Arquitectura

```
┌─────────────────┐        HTTPS/JSON        ┌──────────────────┐
│   App Flutter    │ ───────────────────────▶ │  API Node/Express │
│  (Android/iOS/Web)│ ◀─────────────────────── │      + JWT        │
│  SQLite (offline) │                          └─────────┬────────┘
└─────────────────┘                                     │
                                                          ▼
                                                 ┌──────────────────┐
                                                 │   PostgreSQL     │
                                                 └──────────────────┘
```

- **App**: Flutter (Android/iOS/Web), offline-first con SQLite, `provider` para manejo de estado.
- **Backend**: Node.js + Express, autenticación JWT, subida de archivos con Multer, correo transaccional con Nodemailer.
- **Base de datos**: PostgreSQL (migraciones versionadas en SQL plano).
- **Hosting**: landing en Vercel, API en servidor propio.

## Stack técnico

`Flutter` · `Dart` · `Provider` · `SQLite` · `Node.js` · `Express` · `PostgreSQL` · `JWT` · `Nodemailer`

---

<p align="center">Desarrollado por <a href="https://www.linkedin.com/in/airan-bracamonte">Airan Bracamonte</a></p>
