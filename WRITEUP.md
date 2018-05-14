# WRITEUP

### Step 1: Sensor Noise

Using a break point in `main.cpp` `OnTimer` function, I was able to catch the logs with 99 points. These logs were saved as `Graph1_full.txt` and `Graph2_full.txt`.

With `pandas` `read_csv()` and `describe()` the found standard deviations were:
```
MeasuredStdDev_GPSPosXY = 0.717481
MeasuredStdDev_AccelXY = .512272
```

![Figure 1](./figures/step1.png)

### Step 2: Attitude Estimation

The estimated roll, pitch and yaw were obtained using the quaternion conversion. The baked in function `IntegrateBodyRate` for `Quaternion<float>` takes care of the integration calculation.

Additional yaw radian standardization was done afterwards.

![Figure 2](./figures/step2.png)

### Step 3: Prediction Step

