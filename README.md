# Flux Latent Detailer

![Generated Image 1](https://github.com/rickrender/FluxLatentDetailer/blob/main/FluxLatentDetailer.png)

## Description

This Flux latent upscaler workflow creates a lower-resolution initial pass, then advances to a second pass that upscales in latent space to twice the original size. Latent space manipulations in the second pass largely preserve the original composition, though some changes occur when doubling the resolution. The resolution is not exactly 2x but very close.

This approach seems to help maintain a composition from a smaller size while enhancing fine details in the final passes. Some unresolved hallucination effects may appear, and users are encouraged to adjust values to their liking. 
**I CANNOT PROVIDE SUPPORT FOR THIS, I'M JUST SHARING!**

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
