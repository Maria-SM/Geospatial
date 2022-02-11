```python
import cv2
import numpy as np
```


```python
def nothing (x):
    pass

cv2.namedWindow('colors')
cv2.resizeWindow('colors', 600, 250)
cv2.createTrackbar('LH', 'colors', 0, 255, nothing)
cv2.createTrackbar('MH', 'colors', 255, 255, nothing)
cv2.createTrackbar('LS', 'colors', 0, 255, nothing)
cv2.createTrackbar('MS', 'colors', 255, 255, nothing)
cv2.createTrackbar('LV', 'colors', 0, 255, nothing)
cv2.createTrackbar('MV', 'colors', 255, 255, nothing)

while True:
    image = cv2.imread('C:/Users/marsu/OneDrive/Cambridge_University_Work/Work/clipped.jpg')
    l_h = cv2.getTrackbarPos('LH', 'colors')
    m_h = cv2.getTrackbarPos('MH', 'colors')    
    l_s = cv2.getTrackbarPos('LS', 'colors')
    m_s = cv2.getTrackbarPos('MS', 'colors')    
    l_v = cv2.getTrackbarPos('LV', 'colors')
    m_v = cv2.getTrackbarPos('MV', 'colors')
    
    print(l_h, m_h, l_s, m_s, l_v, m_v)
    
    lower= np.array([l_h, l_s, l_v])
    upper= np.array([m_h, m_s, m_v])
    
    mask = cv2.inRange(image,lower, upper)
    final_result = cv2.bitwise_and(image, image, mask=mask)
    
    cv2.imshow('final output', final_result)
    cv2.imshow('Mask', mask)
    cv2.imshow('Output', image)
    
    cv2.waitKey(1)
```


```python

```