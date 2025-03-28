## Teil 1
Hier habe ich das Image erstellt, und auf mein Git-registry gepusht
![alt text](image-23.png)
![alt text](image-6.png)
Hier habe ich die Textfarbe ausversehen verändert anstadt die Hintergrund.
![alt text](image-27.png)
## Teil 2
Docker compose up -d
![alt text](image-8.png)
Docker Compose down -v
![alt text](image-9.png)
images  
![alt text](image-10.png)
Bei der WEbsite habe ich den Text verändert und das Bild auch noch.
Dazu noch sieht man in der URL, das ich auf die Website mit dem Port 5169 gegangen bin.
![alt text](image-12.png)

Hier habe ich noch die einzelnen Netzwerke und Volumes verändert
![alt text](image-26.png)
## Teil 3
Hier sieht man die Manager Nodes, 1 Leader, und 2 die Reachable sind, während die anderen die Worker Nodes sind

![alt text](image-13.png)
### AWS Instaznen
![alt text](image-24.png)
![alt text](image-25.png)
|Node | Zone |
|-----|------|
|Managernode b1 | us-east 1b|
|Workernode b2 | us-east 1b|
|Managernode c1 | us-east 1c|
|Managernde c2 | us-east c1|
|Workernode c3 | us-east c1|

## Teil 4

---
Hier wurde der Service mit dem neuen Port erstellt.
![alt text](image-28.png)
Die anzahl von Container auf 10 erhöht.
![alt text](image-29.png)

![alt text](image-15.png)

Hier habe ich 2 Container in einem Node gelöscht, und wie wurden durch neue erstetzt.
![alt text](image-20.png)
![alt text](image-16.png)
![alt text](image-17.png)
![alt text](image-18.png)
workernode
![alt text](image-19.png)


## Teil 5
Hier sind alle laufende Container im Stack
![alt text](image-31.png)
Hier habe ich die website mit dem Neuen Port aufgerufen
![alt text](image-34.png)
noch ein weiterer Container
![alt text](image-30.png)
Nach update von Replicas sind nur noch 7 aktiv
![alt text](image-32.png)
Hier habe ich noch den Stack removed
![alt text](image-33.png)