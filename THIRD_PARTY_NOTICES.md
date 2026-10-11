# Third-party components

- **eSpeak NG 1.52.0 (legacy development engine; not in the current Qwen portable release)** — Copyright eSpeak / eSpeak NG contributors. GPL-3.0-or-later. Official Windows engine extracted from the upstream MSI without executing its installer. Full corresponding tagged upstream source archive and GPL text are in the development project's `licenses/`. Project: https://github.com/espeak-ng/espeak-ng
- **CustomTkinter 6.0.0** — Copyright Tom Schimansky and contributors. CC0-1.0. License in `licenses/CustomTkinter-LICENSE.txt`.
- **darkdetect 0.8.0** — BSD-3-Clause. License in `licenses/darkdetect-LICENSE.txt`.
- **Praat-Parselmouth 0.4.7 and its embedded Praat** — GPLv3. Used for traditional TD-PSOLA pitch analysis and resynthesis. License in `licenses/praat-parselmouth/`; complete corresponding source distribution, including embedded Praat, in `licenses/praat-parselmouth-0.4.7-source.tar.gz`. Project: https://github.com/YannickJadoul/Parselmouth
- **NumPy 2.2.6 and SciPy 1.15.3 (portable runtime)** — BSD-3-Clause and bundled dependency licenses. Used for numerical processing, filtering, and resampling. Exact wheel license texts, including bundled BLAS and compiler runtime notices, are preserved in `engine/python/Lib/site-packages/*.dist-info/licenses/`. The GUI development environment uses NumPy 2.5.4 and SciPy 1.18.1; its license texts are additionally preserved in `licenses/`.
- **packaging 26.3** — Apache-2.0 or BSD-2-Clause. License texts in `licenses/packaging/`.
- **Python 3.12.15 (shared GUI/inference runtime) and Python 3.14.5 (optional EXE launcher)** — Python Software Foundation License. Licenses in `licenses/Python-3.12-LICENSE.txt` and `licenses/Python-LICENSE.txt`.
- **Qwen-TTS 0.1.1, transformers 4.57.3, PyTorch/torchaudio 2.8.0+cu128 and their runtime dependencies** — Exact dependency versions are recorded in `运行依赖版本.txt`; original distribution license metadata is retained alongside every included runtime distribution. Qwen model repositories and pinned revisions are recorded in `QWEN使用说明.md` and each model's license files; model quality is unchanged.
- **Tcl/Tk 8.6** — Tcl/Tk permissive licenses. Bundled by the Python distribution; license texts in `licenses/tcl-tk/`.
- **PyInstaller 6.22.3 bootloader** — GPL with the PyInstaller bootloader distribution exception. Text in `licenses/PyInstaller-COPYING.txt`.
- **Microsoft Visual C++ runtime** — Redistributable runtime DLLs detected by PyInstaller from the installed Windows/Python runtime; these remain under Microsoft's license.

VoxCraft / 对白 application source is distributed under GPL-3.0-or-later. The current application's corresponding editable sources and assets are included in `source/`, including the optional launcher and bootstrap. The complete development backup additionally preserves legacy engines, tests and build scripts. To redistribute a modified executable, retain the applicable notices and supply the corresponding modified sources under the relevant license terms.

The packaged application does not upload text or generated speech and does not require a cloud service.

- **bitsandbytes 0.49.2** — MIT License. Included to load separately distributed 8-bit and NF4 model packs. Its license is preserved in the packaged wheel metadata. These packs are project-produced derivatives of pinned Qwen checkpoints; the audio tokenizer/decoder remains unquantized. Official original checkpoints and documentation: https://github.com/QwenLM/Qwen3-TTS
