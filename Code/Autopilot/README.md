# Autopilot Code

- `TraceCreation.py`: builds final trace CSV/TXT files for MELA and Manual.
- `MELA_Abstraction.py`: writes MELA level columns for each direction/configuration.
- `MANUAL_Abstraction.py`: writes manual level columns for each direction/configuration.
- `DecisionTree.py`: learns decision-tree rules for pitchwheel, throttle, and pitchwheel/throttle.
- `AutomataLearning.py`: learns Moore models from final traces and exports DOT models.
- `Evaluation.py`: evaluates learned models on final test traces.
- `Boxplots.py`: creates the final accuracy boxplot.
- `ModelChecking.py`: runs the model-checking workflow scripts.

The main task scripts use:

```python
learning_sets = ["ascend", "descend"]
configurations = ["pitchwheel", "throttle", "pitchwheel_throttle"]
```

Direction names stay inside path variables, not Python filenames.
