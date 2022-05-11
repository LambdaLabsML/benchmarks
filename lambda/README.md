# Setup

```
docker_image=vault.habana.ai/gaudi-docker/1.4.1/ubuntu20.04/habanalabs/tensorflow-installer-tf-cpu-2.8.0:1.4.1-11


sudo docker run --rm -it \
--runtime=habana \
--shm-size=8gb \
-e HABANA_VISIBLE_DEVICES=all \
$docker_image

git clone https://github.com/LambdaLabsML/benchmarks.git

cd benchmarks
git checkout lambda/hl

python3 scripts/tf_cnn_benchmarks/tf_cnn_benchmarks.py --num_gpus=1 --batch_size=32 --model=resnet50 --variable_update=parameter_server

```
