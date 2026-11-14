# Qwen-Image LoRA test workflow

A ComfyUI workflow for testing a Qwen-Image LoRA. It renders one 1024 × 1024 image from a text prompt, with your LoRA applied.

## Files

- `qwen-image-lora-test.json` is the regular workflow. Drag it onto the ComfyUI canvas.
- `qwen-image-lora-test_api.json` is the same workflow in API format, for platforms and scripts that run workflows through an API.

## Models it expects

| Folder | File |
|---|---|
| diffusion_models | qwen_image_fp8_e4m3fn.safetensors |
| text_encoders | qwen_2.5_vl_7b_fp8_scaled.safetensors |
| vae | qwen_image_vae.safetensors |
| loras | your_lora.safetensors (pick your own file in the LoRA loader) |

## Settings

Shift 7, euler sampler, simple scheduler, CFG 3.5, 45 steps, LoRA strength 1.0.

## Testing a LoRA

Write prompts in the words your captions used, for example "linnea the illustrated character smiling".

Render the same prompt and seed twice: once with the LoRA strength at 0 and once at 1.0. The difference is what the LoRA adds.

Camera and lighting words pull the picture toward photography, so we leave them out of test prompts.
