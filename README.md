<div align="center">

# Video Research Lab

### Prompt-as-Code templates for video understanding, generation, transformation, and quality review

**English** · [简体中文](./README.zh-CN.md) · [日本語](./README.ja.md)

</div>

## Overview

Video Research Lab is a function-oriented collection of reusable prompts for AI video workflows. Instead of grouping files by model or provider, it starts from the task a user wants to complete: reverse-engineer a reference video, animate a first frame, replace a subject, continue a clip, transfer motion, or review an existing video prompt.

The repository currently contains **10 prompt workflows**. The prompt library is model-agnostic at the project level; individual templates use terms such as T2VA, I2VA, FL2VA, and Ref2VA when those input relationships matter. Provider-specific capabilities must still be checked before use.

> The project currently focuses on prompt templates. Case studies will be added gradually and are not presented as tested results until their generation records are available.

## Quick Start

1. Choose the function that matches your task.
2. Open its prompt file and read the adjacent usage guide.
3. Copy the complete `<system_protocol>...</system_protocol>` and provide the required video, image, audio, duration, and transformation instructions.
4. Check the returned capability status and unresolved inputs before using the generated prompt in a video tool.

## Prompt Workflows

| # | Function | Input | Output |
|---|---|---|---|
| 01 | [Video Reverse Engineering](./01-视频反推/) | Complete reference video | Evidence-grounded reconstruction prompt |
| 02 | [First-Frame Animation](./02-首帧生成视频/) | First-frame image, motion brief, duration | I2VA prompt that develops forward from the image |
| 03 | [Subject Replacement](./03-替换主体视频/) | Source video and replacement person or object | Two-stage blueprint and reconstructed prompt |
| 04 | [First-and-Last-Frame Generation](./04-首尾帧生成视频/) | First frame, last frame, duration | FL2VA transition path between both anchors |
| 05 | [Video Continuation](./05-视频续写/) | Existing video and continuation brief | Prompt that starts from the verified end state |
| 06 | [Scene Replacement](./06-替换场景视频/) | Source video and target-scene reference | Scene-reconstructed prompt with spatial adaptation |
| 07 | [Video Style Transformation](./07-视频风格转换/) | Source video and style reference | Restyled prompt with content continuity constraints |
| 08 | [Motion Transfer](./08-动作复刻视频/) | Motion-reference video and new subject | Motion blueprint and adapted transfer prompt |
| 09 | [Camera-Movement Transfer](./09-运镜复刻视频/) | Camera-reference video and new content | Camera blueprint and composition-aware prompt |
| 10 | [Video Prompt Review](./10-视频提示词检查/) | Existing prompt and optional references | Findings, validation matrix, and repaired prompt |

See the [template catalog](./docs/templates.md) for scope boundaries and file-level entry points.

## Design Principles

- **Function first:** each directory maps to one user-facing outcome.
- **Structured system protocols:** every prompt uses a consistent XML-style contract for identity, priority, workflow sections, and output rules.
- **Evidence before inference:** templates separate observable facts, user-requested changes, and unknown information.
- **Timeline integrity:** shots, transitions, local generation time, and source-video time are treated explicitly.
- **Reference clarity:** pictures, videos, subjects, and audio assets receive stable roles instead of being mixed together.
- **Portable output:** templates avoid pretending that generic field names are universal provider APIs.
- **Honest verification:** `UNKNOWN`, confirmed absence, and not-applicable states remain distinct.

## Documentation

- [Template catalog](./docs/templates.md)
- [Usage guide](./docs/usage-guide.md)
- [Project scope and limitations](./docs/project-scope.md)
- [Case index](./cases/README.md)
- [Case record template](./cases/_template/README.md)

## Cases

There are currently **0 published cases**. The [case directory](./cases/README.md) is ready for gradual additions. Each future case should retain its inputs, exact prompt, generation conditions, outputs, evaluation, failed attempts, and known limitations.

## Status

The templates have been structurally reviewed for internal consistency. Unless a case includes an explicit generation record, do not interpret its presence in this repository as proof of compatibility with every video model or as evidence of a successful generation run.
