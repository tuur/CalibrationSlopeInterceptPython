# CalibrationSlopeInterceptPython
A simple Python function to calculate calibration slope, calibration intercept, and calibration in-the-large for prediction models with a binary outcome.

### Relevant references (for explanation about how to interpret these measures)
- Van Calster B, Nieboer D, Vergouwe Y, De Cock B, Pencina MJ, Steyerberg EW. [A calibration hierarchy for risk models was defined: from utopia to empirical data](https://doi.org/10.1016/j.jclinepi.2015.12.005). Journal of clinical epidemiology. 2016 Jun 1;74:167-76.
- Van Calster B, McLernon DJ, Van Smeden M, Wynants L, Steyerberg EW. [Calibration: the Achilles heel of predictive analytics](https://doi.org/10.1186/s12916-019-1466-7). BMC medicine. 2019 Dec;17(1):1-7.
- Steyerberg EW, Vergouwe Y. [Towards better clinical prediction models: seven steps for development and an ABCD for validation](https://doi.org/10.1093/eurheartj/ehu207). European heart journal. 2014 Aug 1;35(29):1925-31.

### Disclaimer:
This code is not affiliated with (nor checked by) the authors of the references above. It was verified on multiple datasets that the outputs are the same as the val.prob function in the 'rms' R-package.

### Requirements
(behind brackets is the version in which this script was tested)

For using the calibration_slope_intercept_inthelarge function only:
```
python (3.8)
numpy (1.23.1)
sklearn (1.1.1)
```

For performing the test/comparison with RMS val.prob:
```
rpy2 (3.5.3)
firthlogist (https://github.com/jzluo/firthlogist)
R (4.2.1 arm64)
```


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
