# CalibrationSlopeInterceptPython
Calculation of calibration slope, calibration intercept, and calibration in the large for binary prediction models in Python.

### Short description:
Python function to calculate calibration slope, calibration intercept, and calibration in-the-large for prediction models with a binary outcome.

### Reference (for explanation about how to interpret these measures)
Van Calster B, Nieboer D, Vergouwe Y, De Cock B, Pencina MJ, Steyerberg EW. A calibration hierarchy for risk models was defined: from utopia to empirical data. Journal of clinical epidemiology. 2016 Jun 1;74:167-76.

### Disclaimer:
This code is not affiliated (nor checked by) the authors of the reference above. It was verified on multiple datasets that the outputs are the same as the val.prob function in the 'rms' R-package.


### Example
Code:
```
y = [0, 1, 1, 0, 0, 0, 0, 0, 0, 0]
y_pred = [0.01, 0.01, 0.24, 0.22, 0.02, 0.1, 0.03, 0.12, 0.04, 0.01]
CS, CI, CITL = calibration_slope_intercept_inthelarge(y_pred, y)
print('Calibration slope:', CS, '\nCalibration intercept:', CI, '\nCalibration in the large:', CITL)
```
Outputs:
```
Calibration slope: 0.16386382554885154 
Calibration intercept: -0.8927315726785341 
Calibration in the large: 0.12000000000000001
```
