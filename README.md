<div align="center">

# 🎮 LOADER JB PADRINO

### *El loader con Fase 2 automática para tu PS5*

<br>

![versión](https://img.shields.io/badge/version-v0.7.1-ff1744?style=for-the-badge&logo=playstation&logoColor=white)
![firmware](https://img.shields.io/badge/FW-7.00%20%E2%80%93%2013.60-00e5ff?style=for-the-badge)
![sistema](https://img.shields.io/badge/system-Windows-0078d4?style=for-the-badge&logo=windows&logoColor=white)
![licencia](https://img.shields.io/badge/license-GPL--3.0-3ddc84?style=for-the-badge)
![estado](https://img.shields.io/badge/status-%E2%9C%85%20ESTABLE-4caf50?style=for-the-badge)

<br>

## 📲 **ÚNETE AL CANAL → [t.me/padrinostores](https://t.me/padrinostores)**

<br>

**Un solo archivo. Sin instalación. Sin dependencias.**

</div>

---

## 🚀 Descarga rápida

| Archivo | Tamaño | Para qué |
|---|---|---|
| **`LOADER JB PADRINO.exe`** | 14,3 MB | ⭐ El ejecutable con icono. Descárgalo y ábrelo con doble clic. |

> 💾 **Doble clic y listo.** No hay instalador, no hay configuración previa, no hay carpetas que copiar.

---

## ✨ Características

<table>
<tr>
<td width="50%">

### 🕵️ FW real, siempre
Detecta y muestra la **firmware real** de tu consola en pantalla.
Nada de versiones inventadas ni etiquetas falsas.

</td>
<td width="50%">

### ⚡ Fase 2 automática
Al terminar de cargar el loader principal, lanza **4 payloads extra**
en cadena, con pausa de 4 s entre cada uno.

</td>
</tr>
<tr>
<td width="50%">

### 🛡️ Anti-cuelgue
Si algo falla, el error **se queda impreso en pantalla** y espera a que
pulses `ENTER`. Se acabaron las ventanas que desaparecen solas.

</td>
<td width="50%">

### 🇪🇸 Mensajes en español
Reintentos y avisos con textos claros y amigables,
sin cadenas técnicas crípticas.

</td>
</tr>
<tr>
<td width="50%">

### 🔍 Autodiagnóstico
`--verbose` registra cada evento DNS, TLS y HTTP
para que puedas ver exactamente qué pasa.

</td>
<td width="50%">

### 📦 Bundle embebido
Todos los payloads viajan **dentro del propio ejecutable**.
Nada que descargar aparte, nada que instalar.

</td>
</tr>
</table>

---

## 📦 Payloads incluidos (Fase 2)

Se ejecutan **siempre después** de que el loader principal termina,
uno a uno y en este orden exacto:

| # | Payload | Tamaño | Función |
|---|---|---|---|
| 1 | `ShadowMountPlus_1.7beta11.elf` | 3,6 MB | Montaje de sombra |
| 2 | `ps4mount.elf` | 1,5 MB | Montaje PS4 |
| 3 | `web-file-mgr-v1.14.elf` | 855 KB | Gestor de archivos |
| 4 | `nanodns.elf` | 132 KB | DNS local *(siempre al final)* |

+ **`Loader Padrino.elf`** → el payload principal.

---

## 🕹️ Guía de uso

### 1️⃣ Abre el loader en tu PC
Doble clic en **`LOADER JB PADRINO.exe`**.

Se abrirá una ventana de consola con el título
**`LOADER JB PADRINO`** y verás algo así:

```
  LOADER JB PADRINO  v0.7.1
  PS5 User's Guide host · t.me/padrinostores
  ─────────────────────────────────────────────

  Servidores
    DNS     UDP 53    manuals.playstation.net -> 192.168.1.X
    HTTPS   TCP 443   certificado auto-firmado

  IP PARA EL PS5
    192.168.1.X

    Ajustes  ->  Red  ->  Configurar conexión  ->  Personalizado
    DNS primaria:    192.168.1.X
    DNS secundaria:  8.8.8.8
    Al terminar: INGRESA EL DNS 127.0.0.1 OBLIGATORIAMENTE Y NO LO CAMBIES MAS!

  Esperando el PS5. Abre Ajustes -> Guía del usuario.
```

> ⚠️ **El puerto 443 debe estar libre.** Si algo lo usa, el loader te lo
> dirá y **se quedará esperando a que pulses `ENTER`** para que puedas
> leer el error.

### 2️⃣ Apunta tu PS5 al PC
En la consola: **Configuración → Red → Configurar conexión a Internet →
Usar Wi-Fi → Personalizada → DNS → Manual**

| Campo | Valor |
|---|---|
| DNS primaria | `IP de tu PC` *(la que muestre el loader)* |
| DNS secundaria | `8.8.8.8` |

### 3️⃣ Abre la Guía del usuario
En la PS5: **Configuración → Guía del usuario**.
La consola se conectará a tu PC y el loader arrancará solo.

### 4️⃣ Deja que trabaje
El loader manda el payload principal y, al terminar, ejecuta
la **Fase 2** automáticamente. No toques nada hasta el final.

### 5️⃣ Fija el DNS final (obligatorio)
Cuando el loader termine, entra a la consola y pon:

**Configuración → Red → DNS primaria → `127.0.0.1`**

> 🔒 **Déjalo ahí y no lo vuelvas a cambiar.** El DNS local (`nanodns`)
> es parte del jailbreak; si lo vuelves a Automático pierdes el DNS local.

---

## 🎛️ Opciones avanzadas

| Opción | Descripción |
|---|---|
| `--ip IP` | IP que se entrega al dominio suplantado *(por defecto: auto)* |
| `--target DOMINIO` | Dominio a suplantar *(por defecto: `manuals.playstation.net`)* |
| `--dns-port` | Puerto UDP del DNS *(por defecto: `53`)* |
| `--https-port` | Puerto TCP del HTTPS *(por defecto: `443`)* |
| `--http-port` | Sirve también HTTP plano, p. ej. `8080` para probar en el navegador |
| `--strict-host` | Solo responde peticiones con el `Host` exacto del objetivo |
| `--no-dns` | Desactiva el servidor DNS |
| `--no-https` | Desactiva el HTTPS |
| `--verbose` | Registra cada evento DNS, TLS y HTTP |
| `--extract [DIR]` | Extrae el bundle embebido a una carpeta y sale |
| `--no-color` | Desactiva los colores ANSI |
| `--no-open` | No abre el canal de Telegram al arrancar |
| `--open` | Fuerza abrir el canal aunque se pase cualquier argumento |

**Ejemplos**

```powershell
& ".\LOADER JB PADRINO.exe"                      # uso normal
& ".\LOADER JB PADRINO.exe" --http-port 8080     # probar en el navegador
& ".\LOADER JB PADRINO.exe" --verbose            # log completo
& ".\LOADER JB PADRINO.exe" --extract .\out      # sacar el bundle
```

---

## 🧩 Firmware compatible

Offsets incluidos para **7.00 → 13.60**:

```
7.00  7.01  7.20  7.40  7.60  7.61
8.00  8.20  8.40  8.60
9.00  9.05  9.20  9.40  9.60
10.00 10.01 10.20 10.40 10.60
11.00 11.20 11.40 11.60
12.00 12.02 12.20 12.40 12.60 12.70
13.00 13.20 13.40 13.42 13.60
```

La interfaz muestra **la firmware real** detectada en tu consola en todo momento.

---

## ❓ Preguntas frecuentes

**¿Se cierra solo la ventana en cuanto falla?**
No. Desde ahora, en una **salida con error fatal** el loader imprime el
mensaje y espera a que pulses `ENTER`. En usos normales o con la salida
redirigida a un archivo, sale directamente sin pausar.

**¿Tengo que instalar algo?**
No. Es un ejecutable único con todo embebido.

**¿Puedo probarlo en el navegador del PC?**
Sí: añade `--http-port 8080` y abre `http://127.0.0.1:8080`.

**¿Y si el puerto 443 está ocupado?**
Verás el error en pantalla sin que la ventana desaparezca. Cierra el
programa que lo use (u otro loader abierto) y vuelve a intentarlo.

---

## ⚠️ Aviso

- Uso bajo tu propia responsabilidad, **solo en consolas que te pertenezcan**.
- **No actualices la consola** mientras uses este loader.
- **Nunca inicies sesión en PSN** en una consola con jailbreak.
- Se entrega **tal cual**, sin garantías.

---

## 📜 Licencia

Distribuido bajo **GNU GPL v3.0** — consulta el archivo [`LICENSE`](./LICENSE).

---

<div align="center">

### 📲 **[t.me/padrinostores](https://t.me/padrinostores)**

**LOADER JB PADRINO** · v0.7.1

</div>
