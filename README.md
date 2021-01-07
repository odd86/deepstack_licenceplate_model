# Deepstack licence plate model

This is a model that can be used with [Deepstack](https://github.com/johnolafenwa/DeepStack)

**How to use:**

To use the model download `licence-plate.pt` file inside `/models` folder.

1. Add a folder inside your Deepstack instance (If you run on Host) or mount it in Docker.

2. Run Deepstack with the command `--MODELSTORE-DETECTION "C:/DeepStack/models"`*

**(if "C:/DeepStack/models" is your folder where you have stored the .pt file.)*

3. To use licence plate detection call the endpoint `/v1/vision/custom/licence-plate` with your picture and you get this response if it finds a licence plate:

```python
{
'success': True,
'predictions': [{
  'confidence': 0.93365675,
  'label': 'licence-plate',
  'y_min': 279,
  'x_min': 640,
  'y_max': 340,
  'x_max': 767
  }]
}
```


**Make it better:**

This model is trained to detect Norwegian licence plates, but is tested with various other plates and are working with those. If its needs to train on other plates, please fork this repo and add more data. This can be done by following this guide from [Deepstack Custom Model Guide](https://docs.deepstack.cc/custom-models/datasetprep/index.html).

If you add more data or if you train a new model with this and more data please submit a pull request so we can make a good community licence plate model.
