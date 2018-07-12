import cv2
import numpy as np
import os
import time
import RPi.GPIO as GPIO
from datetime import datetime

flg = True

print('')
recognizer = cv2.face.LBPHFaceRecognizer_create()
recognizer.read('trainer.yml')
print('read train compl')
cascadePath = "../haarcascade_frontalface_default.xml"
faceCascade = cv2.CascadeClassifier(cascadePath);
print('read haar compl')
font = cv2.FONT_HERSHEY_SIMPLEX
#iniciate id counter
id = 0
# names related to ids: example ==> Marcelo: id=1,  etc
names = ['None', 'woojung', 'jooyoung','geunho']
# Initialize and start realtime video capture
cam = cv2.VideoCapture(0)
cam.set(3, 640) # set video widht
cam.set(4, 480) # set video height
# Define min window size to be recognized as a face
minW = 0.1*cam.get(3)
minH = 0.1*cam.get(4)
print('while start')
while True:
    ret, img =cam.read()
    img = cv2.flip(img, -1) # Flip vertically
    gray = cv2.cvtColor(img,cv2.COLOR_BGR2GRAY)

    faces = faceCascade.detectMultiScale(
        gray,
        scaleFactor = 1.3,
        minNeighbors = 4,
        minSize = (int(minW), int(minH)),
        )
#case 1 scaleFactor 1.4 / minNeighbors 6
    for(x,y,w,h) in faces:
        cv2.rectangle(img, (x,y), (x+w,y+h), (0,255,0), 2)
        id, confidence = recognizer.predict(gray[y:y+h,x:x+w])
        # Check if confidence is less them 100 ==> "0" is perfect match
        confidence =round(100 -confidence)
        if (confidence > 40):
            id = names[id]
            confidence = "  {0}%".format(confidence)
            if flg:
            # open_door()
                flg = False
                lock = 11
                GPIO.setmode(GPIO.BOARD)
                GPIO.setup(lock, GPIO.OUT)
                GPIO.output(lock, GPIO.HIGH)
                time.sleep(1)
                GPIO.output(lock, GPIO.LOW)
                GPIO.cleanup()
                file_name = datetime.today().strftime('%Y-%m-%d %H:%M:%S')
                cv2.imwrite('%s.%s.%s.jpg' % (file_name,str(id),str(confidence)),img)
        else:
            id = "unknown"
            confidence = "  {0}%".format(confidence)

        cv2.putText(img, str(id), (x+5,y-5), font, 1, (255,255,255), 2)
        cv2.putText(img, str(confidence), (x+5,y+h-5), font, 1, (255,255,0), 1)

    cv2.imshow('camera',img)
    k = cv2.waitKey(10) & 0xff # Press 'ESC' for exiting video
    if k == 27 or flg == False :
        break
# Do a bit of cleanup
print("\n [INFO] Exiting Program and cleanup stuff")
cam.release()
cv2.destroyAllWindows()
