AI models trained in PyTorch/ONNX often fail to run on custom AI chips due to:
- unsupported operators
- memory constraints
- hardware-specific execution requirements

A minimal compiler pipeline:

Model (OLX/ONNX)
→ Intermediate Representation (IR)
→ Optimization (fusion)
→ Chip-specific executable (CNX)
→ Runtime execution

model-to-runtime-compiler/
├── README.md
├── compiler/
│   ├── parser.py
│   ├── ir.py
│   ├── passes/
│   │   ├── fuse.py
│   │   ├── optimize.py
│   ├── backend/
│   │   ├── didex.py
│   │   ├── nvidia.py
├── runtime/
│   ├── executor.py
├── models/
│   ├── simple_mlp.onnx
│   ├── object_detection.onnx (나중)
├── examples/
│   ├── compile_and_run.py
│   ├── failure_cases.py