# Lab 10: Interpolation Benchmarking (Cloud-to-Edge)

## 📌 Overview
Mathematical transformations (scaling, rotation) create non-integer coordinates. **Interpolation** is the algorithm that guesses the missing pixel values. 

In this lab, you will execute a benchmark on your **GitHub Virtual Machine**. While this cloud VM is much more powerful than a physical Edge device, the **relative performance gap** between algorithms remains the same. A method that is 5x slower on a cloud VM will be catastrophically slow on an Edge device. Let the data drive your engineering decisions.

## 🎯 Learning Objectives
1. Understand the visual and performance trade-offs between `INTER_NEAREST`, `INTER_LINEAR`, and `INTER_CUBIC`.
2. Use `time.perf_counter()` to measure sub-millisecond execution times rigorously in a cloud environment.
3. Analyze the **relative complexity multiplier** of different algorithms.

## 🛠️ Instructions
1. **Prepare Environment**: 
   Ensure you have OpenCV and NumPy installed in your GitHub Codespace: 
   `pip install opencv-python numpy`.
2. **Open the Script**: 
   Open `lab10_interpolation_benchmark.py`. The script generates a 4K high-frequency test pattern dynamically to save bandwidth.
3. **Complete the TODOs**:
   - **TODO 1**: Resize to $224 \times 224$ using Nearest Neighbor.
   - **TODO 2**: Resize using Bilinear.
   - **TODO 3**: Resize using Bicubic.
   - **TODO 4**: Compute the mean and standard deviation of the execution times using NumPy.
4. **Execute & Analyze**: 
   Run the script via `python lab10_interpolation_benchmark.py`.

## ✅ Expected Output
1. **Console Output**: A formatted markdown table showing the Latency and the **Relative Speed Multiplier** for each method.
2. **Visual Artifact**: A file named `benchmark_visual_comparison.png`. Zoom in to observe the aliasing (blockiness) of NEAREST versus the sharpness of CUBIC.
