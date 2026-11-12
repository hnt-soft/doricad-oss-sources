# DoriCAD open-source components · 도리캐드 오픈소스 구성요소

This repository is maintained by **HnT (에이치앤티)** for **HnT DoriCAD (도리캐드)**, a commercial CAD application.
It does **not** contain DoriCAD's own source code. It holds:

1. **Exact source copies of the LGPL libraries shipped with DoriCAD** (unmodified upstream releases), so that every recipient can obtain them
   (LGPL-2.1 §6 · LGPL-3.0 §4 · GPLv3 §6(d)).
2. **Backup copies of files that DoriCAD downloads on first use** (internal AI server and model). DoriCAD always tries the original
   publisher first and uses this copy only when the original is unreachable. Every file is verified by SHA-256 inside DoriCAD.

이 저장소는 에이치앤티(HnT)가 상용 프로그램 **도리캐드(DoriCAD)** 를 위해 관리합니다. **도리캐드 자체의 소스 코드는 들어 있지 않습니다.**

1. 도리캐드에 함께 들어 있는 **LGPL 라이브러리의 원본 소스 사본**(고치지 않은 원본 그대로) — 받으신 모든 분이 소스를 받을 수 있게 합니다.
2. 도리캐드가 처음 쓸 때 내려받는 파일(내부 AI 서버 · 모델)의 **예비 사본** — 원래 배포처를 먼저 쓰고, 막혔을 때만 이 사본을 씁니다.
   도리캐드는 받은 파일을 SHA-256 으로 확인합니다.

## 1. LGPL libraries in DoriCAD · 도리캐드에 든 LGPL 라이브러리

| Library | Version | License | Upstream |
|---|---|---|---|
| Qt | 6.11.0 | LGPL-3.0-only | https://download.qt.io/official_releases/qt/6.11/6.11.0/single/ |
| PySide6 · shiboken6 | 6.11.0 | LGPL-3.0-only | https://download.qt.io/official_releases/QtForPython/pyside6/PySide6-6.11.0-src/ |
| Open CASCADE Technology | 7.9.3 | LGPL-2.1-only WITH OCCT-exception-1.0 | https://github.com/Open-Cascade-SAS/OCCT/releases/tag/V7_9_3 |
| CasADi | 3.8.1 | LGPL-3.0-or-later | https://github.com/casadi/casadi/releases/tag/3.8.1 |
| NLopt | 2.11.0 | LGPL-2.1-or-later (Luksan part) / MIT | https://github.com/stevengj/nlopt/releases/tag/v2.11.0 |

Source archives: **Releases → `lgpl-qt6.11.0-occt7.9.3`** (one release per library set; DoriCAD's notice file links the release that matches each version).

These libraries are installed as **separate files** (DLL · pyd · py) under the `_internal` folder of the DoriCAD installation and can be
replaced by a modified, interface-compatible build. See `licenses\THIRD_PARTY_NOTICES.txt` in the installation folder for the full
license texts and replacement instructions.

이 라이브러리들은 설치 폴더 `_internal` 아래에 **따로 떨어진 파일**로 들어 있어, 인터페이스가 맞는 고친 판으로 바꿔 넣을 수 있습니다.
라이선스 원문과 바꿔 넣는 방법은 설치 폴더의 `licenses\THIRD_PARTY_NOTICES.txt` 에 있습니다.

**Written offer · 소스 제공 약속**: For three years after the last distribution of each DoriCAD version, HnT will provide the complete
corresponding source code of these libraries on request, for no more than the cost of distribution. Please open an issue in this repository.
에이치앤티는 각 판을 마지막으로 배포한 날부터 3년 동안 위 라이브러리의 해당 판 소스 전체를 요청하시는 분께 실비 이하로 제공합니다 — 이 저장소의 Issues 로 요청해 주세요.

## 2. Backup copies of on-demand downloads · 내려받는 파일의 예비 사본

Release **`ai-mirror-b11748`**:

| File | Original publisher | License |
|---|---|---|
| `llama-b11748-bin-win-cuda-12.4-x64.zip`, `llama-b11748-bin-win-cpu-x64.zip` | https://github.com/ggml-org/llama.cpp/releases/tag/b11748 | MIT (llama.cpp authors) |
| `Qwen3.5-4B-Q4_K_M.gguf.001` · `.002` (one file split below GitHub's 2 GiB limit — join in order) · `mmproj-F16.gguf` | https://huggingface.co/unsloth/Qwen3.5-4B-GGUF (GGUF conversion of https://huggingface.co/Qwen/Qwen3.5-4B) | Apache-2.0 (Qwen team, Alibaba Cloud) |

The NVIDIA CUDA runtime package is **not** mirrored here; it is downloaded only from the llama.cpp release page.
NVIDIA CUDA 실행 파일은 여기에 두지 않습니다(llama.cpp 공식 배포처에서만 받습니다).

License texts are attached to each release. · 라이선스 원문은 각 릴리스에 함께 올려 두었습니다.
