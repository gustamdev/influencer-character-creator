---
name: live-action-character-sheet

description: >-
  Gera um único prompt de character sheet fotográfico (prancha de
  continuidade com vistas de corpo inteiro de frente, 3/4, perfil e costas,
  mais closes de rosto, olhos, mãos, prop e detalhes do figurino) para um
  personagem live-action/caricato com realismo fotográfico extremo, pronto
  para Higgsfield, Nano Banana, GPT Image, Midjourney ou Flux. Use sempre
  que o usuário pedir character sheet, model sheet, turnaround, folha de
  personagem, prancha de referência, vistas do personagem, "o personagem de
  vários ângulos", folha de expressões ou referência de consistência para um
  personagem, inclusive logo depois de criar um personagem com a skill
  live-action-character.
---

# Live-Action Character Sheet

You turn a live-action character (a modern cartoon or caricature translated into a real, photographed person) into **one image-generation prompt for a character sheet**: a single image showing the same real person from several angles plus detail close-ups. The sheet exists so the user can keep the character consistent across future posts, edits and videos, so identity consistency between panels matters more than anything else.

**The output is exactly one prompt.** No base-character prompt, no separate negative prompt, no alternatives.

Talk to the user in their language. Write the prompt in English.

## Why a "continuity board" and not a "character sheet"

The words "character sheet", "model sheet" and "turnaround" come from illustration, and image models answer them with drawings, flat colours and labelled diagrams. Describe the sheet as what it would be on a real film set: **the costume department's continuity photos of a cast actor**, nine (or so) real photographs from one studio session, laid out in a clean grid. The layout of a character sheet is kept; the drawn look goes away.

For the same reason, never ask for text, labels, numbers or arrows on the image. Image models garble text, and labels make the board look like a diagram. Panel order is described in the prompt, not written on the image.

## The realism principles (same as live-action-character)

- **Cast, don't render.** Describe a real person whose natural features already resemble the cartoon, with subtle practical makeup or prosthetics only where needed.
- **No stylisation words outside the "Avoid" line**: cartoon, anime, character design, caricature, stylised, render, 3D, Pixar, illustration, sketch, drawing.
- **No fake-quality buzzwords**: ultra-photorealistic, hyper-realistic, 8K, masterpiece, best quality, highly detailed, perfect. Use concrete camera, lens, light and retouching language instead.
- **Exaggeration at the edge of human range**, stated in anatomical terms.
- **Imperfections are mandatory**: at least six concrete ones across skin, hair, clothes and environment. On a sheet they also help identity: the same scar, stain or missing stone repeated across panels anchors the model to one person.
- **One coherent light setup**, identical for every panel.
- **Modern styling**, playful and never mean, no real person's likeness, no brand logos.

## Workflow

### 1. Find the character

Use the first source that exists:

1. A character prompt already in this conversation (e.g. one just made with live-action-character).
2. A file in `characters/` in the working directory. If several exist and the user didn't say which, ask.
3. A description the user gives now.
4. Only a cartoon name or concept: design the character internally following the live-action-character skill's rules (read `~/.claude/skills/live-action-character/SKILL.md` if it is available), then build the sheet. Don't deliver the base prompt separately.

Reuse every concrete detail from the source (measurements, colours, fabrics, imperfections, prop). Don't invent a new outfit or face: a sheet that drifts from the character it documents is useless.

If the user asks for a specific sheet type (expressions only, outfit only, turnaround only, more or fewer panels, a different aspect ratio), follow it. Otherwise use the default layout below. Don't ask questions you can answer with the default.

### 2. Choose the panels

**Default: nine photos, horizontal 3:2.**

- **Top row, four full-body photos, head to toe, same scale, feet on the same baseline:** front, three-quarter, side profile, back. Give each a pose that shows something the others don't: the front has the signature pose and prop; the profile shows nose, posture and the depth of the hair or silhouette; the back shows hair from behind, the back of the garments and how they fall.
- **Bottom row, five close-ups:** head-and-shoulders portrait with the signature expression; extreme close-up of the most distinctive facial feature; one more face detail (mouth, ears, makeup, prosthetic edge, whatever defines the character); the hand holding the signature prop; the most important outfit or accessory detail.

Pick the close-ups for this character's 2-3 defining features. A close-up that doesn't show a defining feature is a wasted panel.

**Other layouts when asked:**

- *Turnaround only:* five full-body photos in one row, 16:9: front, three-quarter left, profile, three-quarter back, back.
- *Expressions:* six head-and-shoulders photos, 3:2, 2 rows by 3, same framing and light; each expression described through eyes, brows and mouth, the signature one first.
- *Outfit and props:* two full-body photos (front and back) plus four to six close-ups of garments, accessories and the prop, hands included where the prop is held.

### 3. Write the prompt

Continuous prose with labelled sections, every bracket filled with concrete detail:

```
Film wardrobe and continuity reference board made of [N] real, unretouched photographs of the same real [age]-year-old [person description], arranged in a clean grid on a plain light-grey background with thin even gutters between photos, [aspect] format. Every photo shows the identical person, face, hair, outfit, accessories and prop, shot in the same studio session with the same lighting. Looks like the costume department's continuity photos of an actor cast for a live-action film, not a costume and not a digital character.

The [person]: [body and proportions in plausible human terms; face shape and asymmetry; hair with product, clumping, flyaways, roots or dye unevenness; each distinctive facial feature in anatomical terms; skin tone with real variation and at least three skin imperfections; makeup or subtle prosthetics if any; the signature expression through eyes, brows and mouth, stated as the expression for every face-visible panel unless a panel says otherwise].

Outfit (identical in every photo): [every garment top to bottom with colour, fabric, fit and a sign of wear; accessories]. Prop: [the signature prop with its own imperfection].

[Row label], [what the row has in common, e.g. "four full-body photos, head to toe, same scale, feet on the same baseline"]:
1. [View]: [pose, where the hands and prop are, what this angle reveals].
2. ...

[Next row label]:
5. [Close-up]: [exactly what is in frame and which textures must be visible].
...

Photography: every photo shot on a Sony A7R V with an 85mm f/1.8 lens at f/8, ISO 100, 1/160s, eye-level, against the same seamless light-grey paper backdrop with faint paper texture, a soft contact shadow under the feet in the full-body shots. Single large softbox key from front left at 45 degrees, white bounce fill on the right, faint hair light from behind; real shadows under the chin, nose and arms[, plus character-specific highlights or shadows]. Natural skin texture with pores and fine vellus hair, true colour with neutral white balance, subtle sensor grain, no retouching, no beauty filter, no skin smoothing. Consistent exposure and colour across all [N] photos.

Consistency: the same face[, the 2-3 defining features] must be identical in all [N] photos and obvious at thumbnail size.

Avoid: cartoon, anime, illustration, 3D render, CGI, character design sheet drawing, stylised, painting, digital art, sketch, plastic skin, waxy skin, smooth skin, airbrushed, beauty filter, glossy skin, perfect symmetry, doll-like face, uncanny valley, mascot costume, cheap cosplay, wig look, impossible proportions, oversaturated, HDR, over-sharpened, glowing light, shadowless lighting, retro or vintage styling, extra fingers, distorted hands, different faces between photos, changing outfit between photos, [character-specific drift terms], overlapping photos, collage effects, busy background, cropped heads or feet in the full-body photos, text, labels, numbers, arrows, watermark, logo.
```

Describe the character once, in "The [person]" and "Outfit" sections, and let the panel lines refer back to it. Repeating the full description per panel makes the prompt long enough that models start to drop details; panels should only add what that angle or crop reveals.

### 4. Quality check before delivering

Silently verify and fix:

- Outside the "Avoid" line: none of cartoon, anime, character design, caricature, stylised, render, 3D, illustration, sketch, hyper-realistic, ultra-photorealistic, 8K, masterpiece, best quality, perfect. ("Character design sheet drawing" belongs only in Avoid.)
- Every detail matches the source character; nothing new was invented that contradicts it.
- The panel count in the opening, the numbered list and the Photography and Consistency lines all agree.
- Full-body panels say head to toe, same scale, same baseline; the back view is described concretely.
- Each close-up shows a defining feature, the prop in hand, or a key outfit detail.
- Hands are relaxed, holding something or in a natural position, with five fingers.
- At least six concrete imperfections, and one light setup shared by all panels.
- No request for text, labels or numbers on the image.
- Nothing retro, no real person's likeness, no brand logos.

## Reply format

Reply with:

1. One line naming the character and the sheet type.
2. The prompt in a single copyable code block.
3. One line: attaching an image of the character (e.g. from the base prompt) as a reference, in tools that accept one, keeps the face identical across panels.

Then save the same prompt to `characters/<character-slug>-sheet.md` in the current working directory (or `-expressions.md`, `-turnaround.md`, `-outfit.md` for the other layouts), unless the user says not to, and mention the path in one short line.

If the user later asks for a change, return one complete, updated prompt, never a partial diff.
