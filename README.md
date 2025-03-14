
### **README.md**  

# 🖧 Configuración de Red en Cisco Packet Tracer 🚀  

Este proyecto muestra la configuración de un **sistema de red en Cisco Packet Tracer**, incluyendo la asignación de direcciones IP, activación de interfaces y configuración de rutas.  

## 📌 1. Descripción del Sistema  

La red configurada en **Cisco Packet Tracer** incluye:  

- **1 Router Cisco** (modelo 2911 o 1841).  
- **1 Switch** para la conexión de dispositivos.  
- **2 PCs o más** para pruebas de conectividad.  
- **Asignación de direcciones IP en subredes específicas**.  

 **Topología de la Red** (basada en la imagen proporcionada):  
- El **router** tiene la IP `200.30.40.1` en la interfaz `FastEthernet0/0`.  
- El **switch** distribuye la conexión a múltiples dispositivos en la red local.  
- Cada **PC** tiene una IP dentro de la subred `200.30.40.0/24`.  
- Se configura una **ruta estática** para la comunicación con redes externas.  

---

## ⚡ 2. Acceder al Modo de Configuración  

Para ingresar al router y comenzar la configuración, usamos:  

```bash
Router> enable
Router# configure terminal
```

Esto nos lleva al modo de configuración global.

---

## 🔧 3. Configurar la Interfaz del Router  

Asignamos una dirección IP a la interfaz principal del router y la activamos:  

```bash
Router(config)# interface FastEthernet0/0
Router(config-if)# ip address 200.30.40.1 255.255.255.0
Router(config-if)# no shutdown
Router(config-if)# exit
```

✅ **Explicación:**  
- `interface FastEthernet0/0` → Accedemos a la interfaz.  
- `ip address 200.30.40.1 255.255.255.0` → Asignamos una IP y la máscara de subred.  
- `no shutdown` → Activamos la interfaz.  

Si la configuración es correcta, aparecerá este mensaje:  
```
%LINK-5-CHANGED: Interface FastEthernet0/0, changed state to up
```

---

## 🌍 4. Configuración de Rutas Estáticas (Opcional)  

Si hay más de una red conectada, configuramos una ruta estática para la salida a internet o a otra red:  


Router(config)# ip route 0.0.0.0 0.0.0.0 200.30.40.2
```
Esto indica que **todo el tráfico desconocido** será enviado a `200.30.40.2` (otro router o gateway).

---

## 🖥 5. Configuración de los PCs  

Cada PC necesita una dirección IP dentro de la misma subred. En cada PC, configuramos:  

- **IP:** `200.30.40.10` (o cualquier IP dentro de `200.30.40.0/24`).  
- **Máscara:** `255.255.255.0`  
- **Gateway:** `200.30.40.1` (IP del router).  

Esto se puede hacer en la configuración de la **tarjeta de red (NIC)** de cada PC en **Packet Tracer**.

---

## 🛠 6. Prueba de Conectividad  

Podemos verificar la conectividad entre dispositivos usando **ping**:  

```bash
PC> ping 200.30.40.1
```
Si todo está bien, veremos respuestas exitosas:  
```
Reply from 200.30.40.1: bytes=32 time<1ms TTL=64
```

También podemos revisar las configuraciones del router con:  

```bash
Router# show ip interface brief
```

---

## 💾 7. Guardar la Configuración  

Para evitar perder los cambios, guardamos la configuración con:  

```bash
Router# write memory
```
o  
```bash
Router# copy running-config startup-config
```

---

## 🎯 8. Conclusión  

Con esta configuración, hemos logrado:  

✅ Establecer la conexión del **router con la red local**.  
✅ Asignar direcciones **IP estáticas** a las interfaces.  
✅ Configurar una **ruta estática** para la comunicación con otras redes.  
✅ Permitir la conectividad entre **PCs y el router**.  

Este es un ejemplo básico, pero se puede expandir con **DHCP, NAT, VLANs y más**. 🚀  


