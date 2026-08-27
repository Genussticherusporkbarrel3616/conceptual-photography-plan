# Conceptual Photography Plan

**English** | [简体中文](README.zh-CN.md)

`conceptual-photography-plan` is a cross-platform Agent Skill for creating original conceptual photography. Starting from a word, a specific object, a source image, or a theme, it expands possible concepts and filters out forced or physically implausible ideas. It generates the corresponding photorealistic image when the host provides an image tool; otherwise it delivers a production-ready prompt.

It looks for a relationship that feels discovered rather than engineered: **familiar object × native action or material behavior × exact position × minimal alteration**. Every successful frame preserves **original object identity → real connection or action → visible functional result**.

> **In one sentence:** Keep the surrealism within the crucial 10% of the relationship, while the other 90% remains grounded in reality.

## Triggering

After the Skill is installed and enabled, it can be triggered explicitly or by a matching natural-language request:

- **Codex:** `Use $conceptual-photography-plan to create two concepts from a banana.`
- **Claude Code:** `/conceptual-photography-plan Create two concepts from a banana.`
- **Claude, Coze, and other compatible hosts:** Ask naturally, for example, `Use conceptual-photography-plan with this source image and select the strongest direction.`
- **Semantic triggering:** Requests involving a specified element, conceptual-photography theme, source-image reinterpretation, precise image correction, or feedback such as “next” and “pass” can load the Skill automatically when the host supports skill discovery.

## Workflow

1. **Understand the input:** Identify the requested element, theme, source image, quantity, and output constraints.
2. **Route source images:** Classify each image as an object anchor, scene base, edit target, or pure style reference.
3. **Expand and screen concepts:** Generate candidates, apply the six hard gates, then rank survivors by fun 70%, emotion or meaning 20%, and visual impact 10%.
4. **Engineer the visual evidence:** Define attachment points, load bearing, material behavior, action path, lighting, and the visible before–contact–after sequence.
5. **Generate or fall back:** Use the host’s available image tool for separate full-bleed 3:4 outputs; when no image tool exists, provide separate production-ready prompts and state that no image was generated.
6. **Inspect and deliver:** Blind-read the actual output, audit skin, materials, asymmetry, light, contact shadows, lens behavior, and grading for AI traces, allow at most one precise correction, and present each selected concept concisely.

## Example Works

<table>
  <tr>
    <td width="33%" align="center">
      <img src="assets/examples/cassette-ponytail.png" alt="Rewind Ponytail" width="100%"><br>
      <strong>Rewind Ponytail</strong><br>
      The cassette retains its winding mechanism, while the tape becomes a ponytail that can literally be rewound.
    </td>
    <td width="33%" align="center">
      <img src="assets/examples/eyebrow-lawn.png" alt="Eyebrow Lawn" width="100%"><br>
      <strong>Eyebrow Lawn</strong><br>
      A miniature lawn mower travels along an eyebrow, showing both the point of contact and the trimmed result.
    </td>
    <td width="33%" align="center">
      <img src="assets/examples/blind-skirt.png" alt="Venetian-Blind Skirt" width="100%"><br>
      <strong>Venetian-Blind Skirt</strong><br>
      The blinds retain their slats, ladder cords, and pull-cord system, taking over the opening and closing function of a skirt.
    </td>
  </tr>
  <tr>
    <td width="33%" align="center">
      <img src="assets/examples/sharpen-candle.png" alt="Sharpen a Candle" width="100%"><br>
      <strong>Sharpen a Candle</strong><br>
      A pencil sharpener genuinely shaves the candle, with the shavings, blade, and wick forming a complete chain of visual evidence.
    </td>
    <td width="33%" align="center">
      <img src="assets/examples/tear-wiper.png" alt="A Wiper for Tears" width="100%"><br>
      <strong>A Wiper for Tears</strong><br>
      A tiny externally mounted wiper follows a tear trail, turning “wiping away tears” into a real mechanical action.
    </td>
    <td width="33%" align="center">
      <img src="assets/examples/apple-corkscrew.png" alt="Uncork an Apple" width="100%"><br>
      <strong>Uncork an Apple</strong><br>
      A corkscrew twists into a skin-covered apple core, preserving the complete sequence of insertion, leverage, and extraction.
    </td>
  </tr>
</table>

These examples use displaced actions, functional substitution, and scale shifts, but all follow the same principle: **form is not decoration; function, action, and result must work together.**

## What It Can Do

- **Element-based concepts:** Start with an element such as a banana, rose, comb, or candle and generate genuinely distinct original directions.
- **Theme-based concepts:** Explore themes such as love, Valentine’s Day, loneliness, or time through relationships that can be communicated in a single photograph.
- **Reference-image driven:** First determine whether the image contains a structurally complete, functional “object anchor.” Preserve its real structure and function whenever possible; use the image only as a style reference when no suitable anchor can be extracted.
- **Scene transformation:** Preserve roughly 80%–90% of the original space, people, perspective, and lighting while changing only one crucial relationship.
- **Logic review:** Check connection points, load bearing, hinges, tool orientation, liquid paths, opening mechanisms, shadows, and cause-and-effect.
- **Continuous iteration:** Understand short feedback such as “next,” “continue,” “pass,” or “keep the person and change only the prop,” while locking all untouched elements.
- **Capability-aware image generation:** Deliver the selected concept and its image together when the host provides an image tool; otherwise deliver a production-ready prompt without fabricating a result.

## Core Method

### 1. Start with the Native Fit

Every concept needs at least:

```text
Familiar object × native action or material behavior × exact position × minimal alteration
```

For example, a lawn mower and an eyebrow share “trimming”; a windshield wiper and tears share “wiping away”; melting ice can form a ring while its native material change supplies the meaning. Generic color or silhouette matching is rejected first.

### 2. Reject First, Then Score

Every candidate must pass six hard gates: object recognition, action or role completeness, a natural connection, physical or role closure, photographic beauty, and originality. A broken critical structure cannot be rescued by a high preference score.

Candidates that pass are ranked using these weights:

- Fun: 70%
- Emotion or meaning: 20%
- Visual impact: 10%

Immediate readability, originality distance, physical or role logic, beauty, and practical shootability remain hard gates outside the weights.

### 3. Turn the Concept into Single-Frame Evidence

The final image should guide the viewer through this sequence:

```text
Original object → contact or connection → visible result
```

If the image depends on a title to make sense, or can only be described as “an object placed somewhere,” the composition does not proceed to generation.

## Installation

### Universal ZIP: Claude, Coze, and Agent Skills Hosts

[Download `conceptual-photography-plan-universal.zip`](dist/conceptual-photography-plan-universal.zip)

The universal package contains only the standard `SKILL.md` entrypoint and its three required reference files. Its ZIP root is the correctly named `conceptual-photography-plan/` folder.

- **Claude:** Upload the ZIP from **Customize → Skills**, or extract the folder to `~/.claude/skills/` for Claude Code.
- **Coze:** Upload the same ZIP with **Upload skill package**; Coze can inspect and repackage the standard structure.
- **Other compatible hosts:** Import or extract the top-level skill folder according to the host's Agent Skills instructions.
- **Image capability fallback:** The Skill generates images when the host provides an image-generation tool. Otherwise it delivers screened concepts and production-ready prompts without claiming that an image was created.

### Option 1: Ask Codex to Install It (Recommended)

Send this message in Codex:

```text
Use $skill-installer to install this Skill from https://github.com/natsany/conceptual-photography-plan.
```

After installation, invoke it in your next conversation turn or in a new task.

### Option 2: Clone with Git

#### Windows PowerShell

```powershell
$skillRoot = if ($env:CODEX_HOME) {
    Join-Path $env:CODEX_HOME 'skills'
} else {
    Join-Path $env:USERPROFILE '.codex\skills'
}

New-Item -ItemType Directory -Path $skillRoot -Force | Out-Null
git clone https://github.com/natsany/conceptual-photography-plan.git `
    (Join-Path $skillRoot 'conceptual-photography-plan')
```

#### macOS / Linux

```bash
skill_root="${CODEX_HOME:-$HOME/.codex}/skills"
mkdir -p "$skill_root"
git clone https://github.com/natsany/conceptual-photography-plan.git \
  "$skill_root/conceptual-photography-plan"
```

The installation directory should contain `SKILL.md` at its root:

```text
conceptual-photography-plan/
├── SKILL.md
├── agents/
│   └── openai.yaml
└── references/
    ├── calibration.md
    ├── logic-audit.md
    └── prompt-patterns.md
```

> The default installation path is `$CODEX_HOME/skills`; if `CODEX_HOME` is not set, `~/.codex/skills` is used. After installation, start a new task so Codex can reload the Skill.

## Usage

Explicitly include `$conceptual-photography-plan` in your prompt, then provide an element, theme, or reference image.

### Generate Two Concepts and Images from One Element

```text
Use $conceptual-photography-plan to create two new concepts based on a banana.
```

### Generate a Specified Number of Concepts from a Theme

```text
Use $conceptual-photography-plan to create four concepts based on “Valentine’s Day” and generate the images directly.
```

### Use a Reference Image

Upload the image first, then send:

```text
Use $conceptual-photography-plan with this reference image, select the strongest concept, and generate a 3:4 image directly.
```

The Skill first determines whether the image is an edit target, a scene base, an object anchor, or a pure style reference. Calling it a “reference image” does not cause the original composition to be copied automatically.

### Make a Precise Edit to the Current Image

```text
Keep the person, scene, and lighting unchanged. Replace only the wiper with a tiny externally mounted prop.
```

Short feedback applies to the currently selected image by default. Unmentioned elements—including composition, people, materials, and lighting—remain locked whenever possible.

### Review Concepts Without Generating Images

```text
Use $conceptual-photography-plan to create two new concepts based on a rose. Show concepts only; do not generate images.
```

## Default Output

- When one element is provided without a quantity, the default output is **2 distinct concepts + 2 corresponding images**, or 2 separate production-ready prompts when the host has no image tool.
- When a source image is uploaded with a request such as “try this,” the default output is **1 strongest direction + 1 image**, or its precise generation/edit prompt when image execution is unavailable.
- When a quantity is specified, each concept receives its own image or prompt; a collage is never used as a substitute for separate outputs.
- Default format: vertical **3:4**, full-bleed, with no white border or rounded corners.
- Default style: photorealistic photography; action-based concepts favor real-life settings and natural light.
- Each image contains only one anomalous relationship, with no explanatory text, arrows, labels, or magical effects.

## Best Suited For

- Original conceptual photography and visual metaphors
- Advertising concepts, editorial photography, and social-media visuals
- Extracting mechanisms from references without producing close imitations
- Reviewing AI-generated images for structural, functional, and physical plausibility
- Producing a visually coherent series built from distinct mechanisms

This is not a “random collage generator.” If a concept cannot be explained in one sentence, recognized in one second, or built with a physically complete real-world structure, the Skill changes direction instead of defending a weak image with a complicated explanation.
