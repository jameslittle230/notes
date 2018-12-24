# Object Detection Clean Setup Installation Instructions

## Set Up the Thing

From `models/research`:

- `object_detection` directory
- `slim` directory
- `setup.py`

Protobufs have to be compiled (`bin` directory will be created)

- Run `wget -O protobuf.zip https://github.com/google/protobuf/releases/download/v3.0.0/protoc-3.0.0-linux-x86_64.zip`
- Run `unzip protobuf.zip`
- Run `./bin/protoc object_detection/protos/*.proto --python_out=.`

Object detection module has to be built (`build` directory will be created)

- Run `python3 setup.py build`
- At some point, `python3 setup.py install` has to be run with the correct options, but I had already done this

PythonPath has to be set up

Fix the code for Python 3

If you're using python3 , add `list()` to `category_index.values()` in `model_lib.py` about line 381: `list(category_index.values())`.

Then you can run `python object_detection/builders/model_builder_test.py` and it should all be good

## Run the Thing

You need a config file and a TFRecord file and a labelmap file

Make sure `object_detection/modeldir/` is empty: `rm -r object_detection/modeldir/*`

The command to begin training:

```bash
PIPELINE_CONFIG_PATH="nbl-tf-test.config"
MODEL_DIR="./object_detection/modeldir"
NUM_TRAIN_STEPS=50000
SAMPLE_1_OF_N_EVAL_EXAMPLES=1

python3 object_detection/model_main.py \
    --pipeline_config_path=${PIPELINE_CONFIG_PATH} \
    --model_dir=${MODEL_DIR} \
    --num_train_steps=${NUM_TRAIN_STEPS} \
    --sample_1_of_n_eval_examples=$SAMPLE_1_OF_N_EVAL_EXAMPLES \
    --alsologtostderr
```
