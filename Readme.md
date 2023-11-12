# StableDiffusion Model to LCM OpenVINO converter

Create a venv and install the requirements.
`pip install -r requirements.txt`

or run `install.bat`

activate the environment
`env/Scripts/activate`

LCM conversion is a two step process.

1. Create LCM-LoRA baked in model and replace the scheduler with LCM
`python lcm-convert.py --no-half --model Lykon/dreamshaper-7 --huggingface --name rupeshs/LCM-dreamshaper-7 --upload`

2. Convert to OpenVINO using `optimum-cli`
`optimum-cli export openvino --model "rupeshs/LCM-dreamshaper-7" "LCM-dreamshaper-v7-openvino`

Thanks [Disty0](https://github.com/Disty0) for the conversion script.
This models can be used with [SDFast CPU](https://github.com/rupeshs/fastsdcpu)