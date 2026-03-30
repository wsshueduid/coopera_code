# COOPERA Benchmark

🖥️ Minimum requirement: 3x GPUs with at least 24 GB VRAM each.

## Main Approach

```bash
# Remember to configure the options and set COLLABORATION_CONFIGS inside the script
CUDA_VISIBLE_DEVICES="x,y,..." python coopera_main/benchmark/main.py [OPTIONS]
```

**Options** 

**Core Configuration**
- `--collab-type[1,2]` - Collaboration type (default: 2).
- `--collab-setting[1,2,3,4]` - Collaboration setting (default: 1).
- `--use-gpt-human[True/False]` - Read human simulation results by GPT; if False, use Qwen3.5-27B (default: True).
- `--use-gpt-robot[True/False]` - Use GPT for robot intention/task discovery; if False, use Qwen3.5-27B (default: True).
- `--start-logic-robot[True/False]` - Restart robot intention/task discovery (default: True).
- `--start-logic-lora[True/False]` - Restart LoRA-based intention/task classification (default: True).

**GPU**
- `CUDA_VISIBLE_DEVICES="x,y"` - GPUs visible to system
- `--gpu-id n` - Single GPU ID for Habitat simulation and computing semantic similarity (default: 0)

## Baselines
```bash
# Direct Prompting
CUDA_VISIBLE_DEVICES="x,y,..." python coopera_main/benchmark/prompting.py [OPTIONS]

# Direct Finetuning
CUDA_VISIBLE_DEVICES="x,y,..." python coopera_main/benchmark/finetuning.py [OPTIONS]

# Oracle
CUDA_VISIBLE_DEVICES="x,y,..." python coopera_main/benchmark/oracle.py [OPTIONS]

# Random
CUDA_VISIBLE_DEVICES="x,y,..." python coopera_main/benchmark/random_.py [OPTIONS]

# Intention Agnostic
CUDA_VISIBLE_DEVICES="x,y,..." python coopera_main/benchmark/ag_intent.py [OPTIONS]

# Human & Context Agnostic
CUDA_VISIBLE_DEVICES="x,y,..." python coopera_main/benchmark/ag_human.py [OPTIONS]
```