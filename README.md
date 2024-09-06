# Flux Latent Upscaler

![Generated Image 1](https://github.com/rickrender/FluxLatentUpscaler/blob/main/Samples/FluxLatentUpscaler_Before_After.png)

## Updates
09/06/24 - Added an alternative version of the Flux Latent Upscaler workflow, this modified version uses Hyper Flux loras and a new clip text encoder made specifically for Flux and SD3, combined these cut inference time from ~280 seconds down to just over 100 seconds on a 4090 with 24GB of VRAM. All credit for this version goes to u/shootthesound for pointing this out and sharing his tests. The Hyper Flux version is labeled "Flux Latent Upscaler - Hyper Flux Loras.json" and can be found in the root of the repo. You need to download the new clip model and the two Hyper Flux loras, direct links to the Huggingface files are embedded in the workflow. Slight degradation in quality but HUGE boost in speed.

## Description

This Flux latent upscaler workflow creates a lower-resolution initial pass, then advances to a second pass that upscales in latent space to twice the original size. Latent space manipulations in the second pass largely preserve the original composition, though some changes occur when doubling the resolution. The resolution is not exactly 2x but very close.

This approach seems to help maintain a composition from a smaller size while enhancing fine details in the final passes. Some unresolved hallucination effects may appear, and users are encouraged to adjust values to their liking. 

Seed Modulation will adjust the 3rd pass slightly allowing you to skip over the previous passes for slight changes to the same composition, this 3rd pass takes ~112 seconds on my RTX 4090 with 24GB of VRAM. It's taking the fixed seed from the first pass and mixing it with a new random seed which helps when iterating if there are inconsistencies. If something looks slightly off, try a reroll.

All of the outputs in the examples have a film grain effect applied, this helps with adding an analog film vibe, if you don't like it just bypass that node.

The workflow has been tested with photo-style images and demonstrates Flux's flexibility in latent upscaling compared to earlier diffusion models. This imperfect experiment offers a foundation for further refinement and exploration. My hope is that you find it to be a useful part of your own workflow. No subscriptions, no paywalls and no bullshit. I spend days on these projects, this workflow isn't perfect and I'm sure I missed something on this first version. This might not work for everyone and I make no claims that it will. Latent upscaling is slow and there's no getting around that without faster GPUs.

You can see A/B comparisons of 8 examples on my website: https://renderartist.com/portfolio/flux-latent-upscaler/

**JUST AN EXPERIMENT - I DO NOT PROVIDE SUPPORT FOR THIS, I'M JUST SHARING!**

## Resources

This workflow uses `araminta_k_flux_koda.safetensors` which can be found at CivitAI.
[https://civitai.com/models/653093/Koda%20Diffusion%20(Flux)](https://civitai.com/models/653093/Koda%20Diffusion%20(Flux)) -- Amazing lora!

The Kodachrome LUT file can be downloaded from here:
[https://www.freepresets.com/product/free-lut-kodachrome-lookup-table/](https://www.freepresets.com/product/free-lut-kodachrome-lookup-table/)

LUT goes into ComfyUI\custom_nodes\ComfyUI_essentials\luts, if you are using cubiq's comfy_essential nodes like in this workflow.

## Setup

The Flux.1 checkpoint used in this workflow is the dev version. If you're missing any custom nodes or get errors/red nodes:

1. Click manager
2. Click on "Install Missing Custom Nodes"
3. When the installation finishes, click "Restart" as instructed
4. Reload the workflow

## Performance

I'm using an RTX 4090 with 24GB of RAM. Each image takes approximately ~280 seconds.
If you find this workflow to be helpful please consider supporting my work by buying me a coffee or two. 

https://ko-fi.com/renderartist

## License

If you modify and share this workflow, all I ask is that you credit me.
https://renderartist.com
https://www.instagram.com/renderartist/
https://www.x.com/renderartist/
