# Smart-public-restroom-iot
import RPi.GPIO as GPIO
import time

# Set up GPIO
GPIO.setmode(GPIO.BOARD)
PIR_PIN = 7
GPIO.setup(PIR_PIN, GPIO.IN)

# Function to detect motion
def motion_detected(channel):
    print("Motion detected!")

# Add event detection for motion sensor
GPIO.add_event_detect(PIR_PIN, GPIO.RISING, callback=motion_detected)

try:
    while True:
        time.sleep(1)

except KeyboardInterrupt:
    print("Exiting...")
    GPIO.cleanup()
