---
name: image-edit-prompts
description: Write precise AI image-editing prompts for the 10 core operations (enhance, background swap, color correction, object removal, text overlay, recolor, resize/outpaint, shadows, style transfer, final polish). Use when the user wants to edit or generate an image with an AI tool and needs the prompt written for them.
---

# Image-Edit Prompts

Turn a vague editing wish into a prompt an image model can actually execute. One operation per prompt; chain prompts for multi-step edits.

## The universal recipe

`[operation] + [what to change] + [what must NOT change] + [quality/realism anchors]`

The "must not change" clause is what separates a clean edit from a mangled one. Always include it.

## The 10 operations — templates

1. **Enhance quality** — "Enhance this image: increase sharpness and fine detail, balance exposure, recover shadow and highlight detail. Keep composition, colors and subject identity exactly as they are. Photorealistic, no over-smoothing."
2. **Change background** — "Replace the background with [new scene]. Keep the subject completely unchanged: same pose, lighting direction on the subject, edge detail and hair strands. Match the subject's lighting and color temperature to the new background so it looks naturally photographed there."
3. **Color correction** — "Color-correct: neutral white balance, natural skin tones, balanced contrast, no crushed blacks or clipped highlights. Premium editorial look. Do not alter composition or any objects."
4. **Remove objects** — "Remove [object] and reconstruct what's behind it naturally — continue the [surface/texture] seamlessly. No smudges, no traces, no leftover shadows from the removed object."
5. **Add text** — "Add the text '[TEXT]' in [position], bold modern sans-serif, [color], strong contrast against the background. Clear hierarchy: [main line] large, [subline] smaller. Do not warp or cover the subject."
6. **Change colors** — "Change the [object]'s color from [X] to [Y]. Preserve original texture, material reflections, shading and lighting exactly — only the hue changes. Everything else untouched."
7. **Resize / extend** — "Extend this image to [ratio/dimensions] by outpainting: continue the scene naturally on [sides], matching lighting, grain and perspective. Keep the original content unchanged and centered on [subject]."
8. **Add shadows** — "Add a realistic shadow for [subject]: light comes from [direction], so the shadow falls [direction], soft-edged, fading with distance, matching the scene's other shadows in darkness and color."
9. **Style transfer** — "Re-render this image in [cinematic / anime / oil painting / 3D render] style. Preserve the subject's identity, pose and composition; translate colors and textures into the style. [Style-specific anchors: film grain + teal-orange grade / clean line art + cel shading / visible brush strokes]."
10. **Final polish** — "Refine to a flawless professional finish: clean edges, consistent lighting, remove artifacts, subtle micro-contrast. Change nothing about content or composition."

## Rules

- One edit per prompt. For "change the background AND remove the bin", run two passes and say so.
- Ask which tool they're using only if it changes syntax (e.g. some tools need `--ar 16:9` style flags for resize).
- If the user gives an image, describe the specifics into the template (light direction, surface to reconstruct) instead of leaving placeholders.
- Warn when an edit is likely to fail (tiny text, faces through heavy style transfer, removing >30% of the frame) and suggest the safer sequence.
