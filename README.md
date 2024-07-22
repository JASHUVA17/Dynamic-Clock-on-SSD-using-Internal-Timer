# Dynamic-clock-on-SSD-using-internal-timer

Description
This project implements a dynamic and configurable clock on an SSD (Seven Segment Display) using the internal timer of a microcontroller. The clock supports real-time clock functionality and a configuration mode for setting the time.

Features
1. **Initial Start:**
   - Upon power on or reset, the clock initializes and starts at 00:00.

2. **Blinking Decimal Point:**
   - The decimal point of the hours field (one’s place) blinks every 500 milliseconds (0.5 Hz) to indicate active timekeeping.

3. **24-Hour Format:**
   - The clock displays time in a 24-hour format.

4. **Configuration Mode:**
   - Enter configuration mode by pressing the Set/Edit key (DKS4).
   - In configuration mode, the minute field blinks every 500 milliseconds.

5. **Field Selection:**
   - Use the Choose Field key (DKS3) to cycle through the fields (hours and minutes). The selected field blinks at a rate of 500 milliseconds, indicating it is selected for editing.

6. **Time Adjustment:**
   - Use the Increment key (DKS1) to increase the value of the selected field.
   - Use the Decrement key (DKS2) to decrease the value of the selected field.
   - The Increment and Decrement keys are level-triggered for precise control.

7. **Run Mode:**
   - After setting the time, press the Set/Edit key (DKS4) again to start the clock, entering run mode.
   - In run mode, only the Set/Edit key (DKS4) is active; other keys are disabled to prevent accidental changes.

Inputs
- **DKS1 (Digital Keypad Switch 1):** Increment key
- **DKS2 (Digital Keypad Switch 2):** Decrement key
- **DKS3 (Digital Keypad Switch 3):** Choose Field key
- **DKS4 (Digital Keypad Switch 4):** Set/Edit key

Functional Flow
1. **Power On/Reset:**
   - Initialize the clock to 00:00.
   - Start the internal timer.

2. **Run Mode:**
   - Display the current time.
   - Blink the decimal point of the hours field every 500 milliseconds.

3. **Enter Configuration Mode:**
   - Press the Set/Edit key (DKS4).
   - Minute field starts blinking every 500 milliseconds.

4. **Field Selection:**
   - Use the Choose Field key (DKS3) to select either hours or minutes field.
   - The selected field blinks every 500 milliseconds.

5. **Adjust Time:**
   - Use Increment (DKS1) or Decrement (DKS2) keys to adjust the selected field.
   - Changes are immediately reflected on the display.

6. **Exit Configuration Mode:**
   - Press the Set/Edit key (DKS4) to save changes and enter run mode.
   - Resume normal clock operation with the newly set time.
     
Implementation Notes
- Ensure the internal timer is configured correctly to achieve the required 500 milliseconds blinking interval.
- Debounce the keypad switches to prevent accidental multiple triggers.
- Maintain a clear distinction between configuration and run modes to avoid user confusion.
