This ReadMe contains instruction for  Seq-to-Seq model converstion from Tensorflow to ONNXRuntime. 

Step 1 - Download the BERT model from from googleapis using the following command.
 -> !wget https://storage.googleapis.com/bert_models/2018_10_18/uncased_L-12_H-768_A-12.zip

Step 2 - Download the Benchmarking dataset  called SQuAD for the official Implementation and Benchmark testing of BERT.
-> !wget -q https://storage.googleapis.com/bert_models/2018_10_18/uncased_L-12_H-768_A-12.zip

Step 3 - Fine-tune the BERT model on SQuAD model using run_squad.py script.

Step 4 - After fine-tuning, Create an Inference Graph using the squad serving function.

Step 5 - Export the model from the Inference graph to convert it to ONNX format.

Step 6 - Convert the tf model to ONNX format using tf2onnx lib.

Step 7 - Run and verify the ONNX implementation of BERT using ONNXRuntime lib.

---------------------------
# Post-processing Optimization of the bert.onnx model.

Step 8 - Clone the official implementation of Onnx for post-Optimization for PyTorch, Keras, Tensorflow.
-> !wget -O ./bert_op_scripts/bert_model_optimization.py https://raw.githubusercontent.com/microsoft/onnxruntime/master/onnxruntime/python/tools/bert/bert_model_optimization.py

Step 9 - Choose the framework of your choice and Flag the framework=True.

Step 10 - Optimize onnx version of BERT for Half-precision (fp32) and for CPU(x86) using bert_model_optimization.py script and passing 
            correct parameters.

Step 11 - Run the inference on CPU and GPU version of BERT and compare the results. 
