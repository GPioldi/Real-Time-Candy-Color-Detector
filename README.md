# Candy Color Detector 🍬🎨

A **light‑weight open‑source tool** that recognizes candy colors **in real time** through a webcam – designed for the production lines of a leading Italian candy company.  
Built on **OpenCV** and the **HSV** color space to keep detection robust under changing lighting conditions.

> **Proven in the field**  
> The solution was fully tested on a real manufacturing cell, running on a **Raspberry Pi 4 Model B (8 GB RAM)** connected via Profinet to a **Siemens S7‑1200 PLC**.  
> Expect industrial‑grade reliability straight out of the box.

---

## 📂 Repository structure

| File | Purpose | Short description |
|------|---------|-------------------|
| `candy_color_detector.py` | **Main script** | Captures webcam video, reads the pixel at the frame center, converts it to HSV and assigns a color label (RED, ORANGE, YELLOW, GREEN, BLUE, VIOLET) while displaying the result on screen. |
| `hsv_color_picker.py` | **Calibration utility** | Opens a window with three sliders (H, S, V). Adjust them to preview the resulting color in real time – great for quickly finding the best HSV threshold for your candies or lighting. |
| `README.md` | Documentation | This guide. |

---

## 🚀 Quick install

```bash
# 1. Clone the repo
git clone https://github.com/GPioldi/Real-Time-Candy-Color-Detector.git
cd candy-color-detector

# 2. (Optional) create and activate a virtual env
python -m venv .venv
source .venv/bin/activate   # Windows: .venv\Scripts\activate

# 3. Install dependencies
pip install opencv-python numpy
```

---

## ▶️ Usage

### 1. Detect colors
```bash
python candy_color_detector.py
```
* Center the candy under the crosshair (the dot in the middle).  
* The detected color name appears at the top together with a white background box and its BGR components.

### 2. Custom calibration
```bash
python hsv_color_picker.py
```
* Move the **H**, **S** and **V** sliders until the preview square matches your candy’s color.  
* Note the values or edit the thresholds dictionary inside `candy_color_detector.py` to fine‑tune the classification.

---

## 🛠️ Customization

* **HSV thresholds** – edit the `if hue_value < ...` section in `candy_color_detector.py` to match new flavors or shades.  
* **Resolution** – tweak `CAP_PROP_FRAME_WIDTH/HEIGHT` if you need lighter or sharper output.  
* **ROI vs single pixel** – swap the single‑pixel read with an average over a small rectangle for extra noise robustness.

---

## 🤝 Contributing

1. Fork the project  
2. Create a branch: `git checkout -b feature/your-feature-name`  
3. Commit and push  
4. Open a **Pull Request** describing your change

---

## 📄 License

Released under the **MIT License** – feel free to use, modify and distribute it as long as you keep the same license and credit the original author.

Happy coding (and candy testing)! 🍭
