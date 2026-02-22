# camera_py

<br />
<br />

Configurar cuenta tapo: 
Selecciona dispositivo tapo  **>** Ajustes avanzado > cuenta la camara

Direccion de la ip:
Selecciona dispositivo tapo > Información del dispositivo


<br />
<br />


```py
import cv2

user = 'camtap24'
password = 'Vm919293'
ip_adress = '192.168.1.142'

tipo_stream = 'stream2' # ó stream1 (más grande)

rtsp_url = f"rtsp://{user}:{password}@{ip_adress}:554/{tipo_stream}"

cap = cv2.VideoCapture(rtsp_url)

while True:
    ret, frame = cap.read()
    if not ret:
        print("No se pudo leer frame")
        break

    cv2.imshow("Tapo C200", frame)

    if cv2.waitKey(1) & 0xFF == ord('q'):
        break

cap.release()
cv2.destroyAllWindows()
```



<br />
<br />
<br />
<br />
<br />
<br />
<br />

