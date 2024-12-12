# code_generation
!git clone https://github.com/towhidultonmoy/code_generation.git


!pip install aiohttp numpy tqdm pytest datasets torch transformers


cd code_generation


!mkdir tutorial



!python3 automodel.py --name "facebook/incoder-6B" --root-dataset humaneval --lang java --temperature 0.2 --batch-size 20 --completion-limit 10 --output-dir-prefix tutorial --input-limit 5


cd evaluation/src


!python3 main.py --dir /content/code_generation/tutorial --output-dir /content/code_generation/tutorial --recursive


cd ../


cd ../


!python3 pass_k.py ./tutorial/*

