### Step 5: Save and Download the Trained Model

After completing the training process, both model weight files were saved successfully:

- **best.pt:** Contains the weights that achieved the best validation performance during training.
- **last.pt:** Contains the weights from the final training epoch.

Both files were copied to the `/kaggle/working/` directory and are approximately 5.29 MB each.

**Which File Is Better for Deployment?**

The `best.pt` file is preferred for final predictions and deployment because it represents the model's best validation performance during training.

**Why Is best.pt Preferred?**

It provides the best-performing saved checkpoint based on validation results, rather than simply representing the final training epoch.

**How Can the Weights Be Reused?**

The saved weights can be loaded later in another notebook or application without repeating the entire training process:

```python
from ultralytics import YOLO

model = YOLO("best.pt")
```

The model can then be used to detect objects in new images or videos.