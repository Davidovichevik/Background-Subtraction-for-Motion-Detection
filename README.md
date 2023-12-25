# Background-Subtraction-for-Motion-Detection
Implement background subtraction for motion detection in a video stream. Code:
import cv2

cap = cv2.VideoCapture(0)
fgbg = cv2.createBackgroundSubtractorMOG2()

while True:
    ret, frame = cap.read()

    fgmask = fgbg.apply(frame)

    # Implement further processing on fgmask (e.g., contour detection, tracking)

    cv2.imshow('Motion Detection', fgmask)

    if cv2.waitKey(1) & 0xFF == ord('q'):
        break

cap.release()
cv2.destroyAllWindows()
