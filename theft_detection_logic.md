
# Accident Detection Algorithm

1. Read MPU6050 accelerometer data
2. Convert raw values to g-force
3. Calculate total acceleration magnitude
4. Compute roll and pitch orientation
5. Trigger accident if:
   - acceleration > 2.8g
   - orientation change > 55°
