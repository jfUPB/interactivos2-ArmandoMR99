### Actividad 4

## ¿Cómo funciona webRTC?


***¿Qué es webRTC?***
- WebRTC, que significa "Web Real-Time Communication", es una tecnología que permite a las aplicaciones web y móviles comunicarse en tiempo real mediante audio, video y datos
directamente entre navegadores, sin necesidad de plugins o software adicional.

***¿Cómo funciona webRTC?***
- WebRTC funciona estableciendo conexiones directas entre dos dispositivos (peers), permitiendo la transmisión de audio, video y datos. Para ello, utiliza una serie de
protocolos y APIs que gestionan la captura de medios, la transmisión de datos y el manejo de la red.

***¿Qué es un peer connection?***
- Una "peer connection" es el enlace directo establecido entre dos dispositivos que utilizan WebRTC. A través de esta conexión, los dispositivos pueden intercambiar flujos de audio,
video y datos en tiempo real.

***¿Qué es un data channel?***
- Un "data channel" en WebRTC es un medio para enviar datos arbitrarios (como mensajes de texto o archivos) directamente entre dos dispositivos conectados.
Esto permite funcionalidades como chats en tiempo real o transferencia de archivos dentro de aplicaciones WebRTC.

***¿Qué es un media stream?***
- Un "media stream" es una colección de pistas de medios, como audio o video, que se pueden transmitir entre dispositivos. Por ejemplo, una videollamada típica tendría dos pistas:
una de video y otra de audio.

***¿Qué es un ICE server?***
- Un servidor ICE (Interactive Connectivity Establishment) ayuda a los dispositivos a descubrir la mejor manera de conectarse entre sí, especialmente cuando están detrás de
firewalls o routers con NAT. ICE recopila posibles direcciones y métodos de conexión para establecer la comunicación.

***¿Qué es un STUN server?***
- Un servidor STUN (Session Traversal Utilities for NAT) permite que un dispositivo descubra su dirección IP pública y cualquier restricción impuesta por el router o firewall.
Esto es esencial para que dos dispositivos puedan conectarse directamente cuando están en redes diferentes.

***¿Qué es un TURN server?***
- Un servidor TURN (Traversal Using Relays around NAT) actúa como intermediario para retransmitir datos entre dos dispositivos cuando una conexión directa no es posible.
Aunque introduce más latencia, garantiza que la comunicación se establezca incluso en redes muy restrictivas.

***¿Qué es un signaling server?***
- Un servidor de señalización gestiona el intercambio inicial de información entre dos dispositivos que desean establecer una conexión WebRTC. Aunque WebRTC no define un protocolo
específico para la señalización, comúnmente se utilizan WebSockets o HTTP para este propósito.
























