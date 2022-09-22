# -*- coding: utf-8 -*-

import cv2
import numpy as np


##################



cap = cv2.VideoCapture(0)

width = int(cap.get(cv2.CAP_PROP_FRAME_WIDTH))
height = int(cap.get(cv2.CAP_PROP_FRAME_HEIGHT))

x = width // 2
y = height // 2




#####################

while True:
    ret, frame = cap.read()
    
    gray = cv2.cvtColor(frame, cv2.COLOR_BGR2GRAY)
    gray_flip = cv2.flip(gray,1)
    
    med = np.mean(gray_flip)
    
    blurred = cv2.blur(gray_flip, ksize=(3,3))
    
    edges = cv2.Canny(image=blurred, threshold1=med*0.5, threshold2=med*1.5)
    
    
    cv2.imshow('test', edges)
    
    if cv2.waitKey(1) & 0xFF == ord('q'):
        print('break')
        break
    
cap.release()
cv2.destroyAllWindows()

