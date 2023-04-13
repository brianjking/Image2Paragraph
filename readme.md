<p align="center">
  <img src="examples/logo.png" alt="Your Image Description" width=800>
</p>

# Transform Image Into Unique Paragraph 
**(Can run on 8GB memory GPU)**

<p align="center">
  <img src="examples/gpu_memory.png" alt="Your Image Description" width=600>
</p>

![](examples/introduction.png)


## Visualization
<p align="center">
  <img src="output/2_result.png" alt="Your Image Description" width=600>
</p>
<p align="center">
  <img src="output/3_result.jpg" alt="Your Image Description" width=600>
</p>
<p align="center">
  <img src="output/4_result.jpg" alt="Your Image Description" width=600>
</p>

##  Installation

Please find installation instructions in [install.md](install.md).

## 1. News
### Done
- GRIT example.
- ControNet, BLIP2.

### Doing
- Support Segment Anything for fine-grained semantic.
- Replace ChatGPT with own trained LLM.
- Show retrieval result in gradio.

## 2. Start

### Simple visualization

```bash
export OPENAI_KEY=[YOUR KEY HERE]
python main.py  --image_src [abs_path] --out_image_name [out_file_name]
```

like
```bash
python main.py --image_src "/Code/Image2Paragraph/examples/3.jpg" --out_image_name "output/3_result.jpg"
```

The generated text and image are show in "output/".

**Note: Use GPT4 for good result as GPT3.5 miss the position information sometime.**

## Use gradio directly

```bash
python main_gradio.py
```

![](examples/gradio_visualization.png)



## 3. Retrieval Result on COCO

| Method  | Trainable Parameter | Running Time  |  IR@1   | TR@1|
|---|---|---|---|---|
| Image-text  | 230M | 9H |  43.8 |  33.2 |
|Generated Paragraph-text| 0 |5m|__49.7__|__36.1__|


Interesting, we find compress image into paragraph. The retrieval result is even better than use source image.

## Acknowledgment

This work is based on [ChatGPT](http://chat.openai.com), [BLIP2](https://huggingface.co/spaces/Salesforce/BLIP2), [GRIT](https://github.com/JialianW/GRiT),  [OFA](https://github.com/OFA-Sys/OFA),[Segment-Anything](https://segment-anything.com), [ControlNet](https://github.com/lllyasviel/ControlNet).
