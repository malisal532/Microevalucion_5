  

---# 🖧 Configuración de Router Cisco en Packet Tracer 🚀

Este documento explica paso a paso cómo configurar un **router Cisco** en **Packet Tracer**, incluyendo asignación de IP, activación de interfaces y configuración de rutas.

---

## ⚡ 1. Acceder al Modo de Configuración

Para iniciar sesión en el router y entrar en modo de configuración global:

```bash
Router> enable
Router# configure terminal
```

---

## 🔧 2. Configurar la Interfaz de Red  

Asignamos una dirección IP a la interfaz **FastEthernet0/0** y la activamos:  

```bash
Router(config)# interface FastEthernet0/0
Router(config-if)# ip address 200.30.40.1 255.255.255.0
Router(config-if)# no shutdown
Router(config-if)# exit
```

✅ **Explicación:**  
- `interface FastEthernet0/0` → Entramos a la interfaz.  
- `ip address 200.30.40.1 255.255.255.0` → Asignamos la dirección IP y la máscara de subred.  
- `no shutdown` → Activamos la interfaz (por defecto está apagada).  

Si todo está bien, veremos:  
```
%LINK-5-CHANGED: Interface FastEthernet0/0, changed state to up
```

---

## 🌍 3. Configurar una Ruta Estática (Opcional)  

Si queremos que el router sepa cómo enviar tráfico a otras redes, añadimos una ruta por defecto:  

```bash
Router(config)# ip route 0.0.0.0 0.0.0.0 200.30.40.2
```
Esto redirige el tráfico desconocido a **200.30.40.2** (otro router o gateway).

---

## 💾 4. Guardar la Configuración  

Para evitar perder los cambios después de un reinicio, guardamos la configuración con:

```bash
Router# write memory
```
o  
```bash
Router# copy running-config startup-config
```

---

## 🎯 Conclusión  

¡Listo! Ahora el router está configurado con una dirección IP, la interfaz activada y una ruta estática opcional.  
Este es el primer paso para construir una red funcional en **Cisco Packet Tracer**. 🚀  

📌 **Si necesitas más configuraciones, abre un issue o contribuye al repositorio.**  
```

---

Este archivo README es compacto y directo, **listo para subir a GitHub**. 📂  
📌 **¿Quieres agregar más detalles o imágenes?** 🚀
