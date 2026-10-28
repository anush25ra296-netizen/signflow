# SignFlow ResNet-50 conversion

The repository includes a Google Colab notebook that exports the MIT-licensed Hugging Face model `Abuzaid01/asl-sign-language-classifier` from PyTorch to ONNX.

## Run the conversion

1. Open the [conversion notebook in Google Colab](https://colab.research.google.com/github/anush25ra296-netizen/signflow/blob/main/tools/Convert_ResNet50_ASL_to_ONNX.ipynb).
2. Choose **Runtime → Run all** and wait for the ONNX parity check to pass.
3. Download `signflow_resnet50_onnx.zip`. It contains `model.onnx`, `labels.json`, and `preprocessing.json`.
4. Upload those files to a public model repository that you control and supports cross-origin browser requests (CORS).
5. Once the model URL is available, SignFlow can be updated to load the ONNX model using ONNX Runtime Web and feed its predictions into the letter-to-word builder.

## Important

- This notebook converts the model; it does not automatically publish the ONNX weights to SignFlow.
- The model has 29 classes: A–Z, `del`, `nothing`, and `space`.
- The model is trained for static hand-sign images. It does not by itself solve motion-based recognition for J and Z.
- Verify the exported model in the notebook before deploying. Do not treat reported dataset accuracy as guaranteed real-world accuracy.
- The model repository identifies its license as MIT: [model card and files](https://huggingface.co/Abuzaid01/asl-sign-language-classifier).
