# Foggy-generation-dissertation-KCI-
한국교통대학교 EVLAB KCI 논문 Foggy generation dissertation
-심사중-

Depth-Aware 3D Fog Synthesis with Temporal Consistency

Official implementation of the paper
“Depth-Aware 3D Fog Synthesis with Temporal Consistency”

📄 Paper

Depth-Aware 3D Fog Synthesis with Temporal Consistency
(깊이 기반 3D 안개 합성과 시간적 일관성)

This repository provides an implementation of the 3D volumetric fog synthesis framework proposed in our paper.
The method generates spatially and temporally coherent non-homogeneous fog by combining:

3D volumetric noise generation

Depth-aware transmission modeling

Temporal filtering in space-time domain

🔍 Abstract (Short)

Conventional fog synthesis methods are mainly limited to 2D image-space processing, resulting in insufficient depth perception and severe temporal flickering in video sequences.
This work proposes a depth-aware 3D fog synthesis method that constructs a non-homogeneous volumetric fog field in space-time and integrates it with a depth-dependent transmission model.
By applying 3D FFT-based Gaussian filtering, the proposed method ensures temporal consistency while preserving realistic volumetric appearance.

🧠 Method Overview

The proposed framework consists of four main stages:

1. 3D Volumetric Fog Field Generation

Generate random Gaussian noise in space-time volume

Apply 3D FFT

Suppress high-frequency components using a 3D Gaussian filter

Recover a smooth volumetric fog density field via inverse FFT

2. Contrast & Gamma Normalization

Control fog heterogeneity using contrast and gamma parameters

Simulates varying absorption coefficients of participating media

3. Depth-Aware Transmission Modeling

Depth-dependent attenuation modeled using:

Exponential function

Sigmoid function (optional)

Non-homogeneous fog density and depth attenuation are combined multiplicatively

4. Image Rendering

Final fog image synthesized using Koschmieder’s atmospheric scattering model

📐 Mathematical Formulation

The final transmission map is defined as:

Tfinal​(t,y,x)=Tbase​(t,y,x)⋅Tdepth​(y,x)

The foggy image is rendered as:

Ihazy​=I⋅Tfinal​+A(1−Tfinal​)

where 𝐴
A denotes atmospheric light.

⏱️ Temporal Consistency

Unlike 2D noise-based methods that generate fog independently per frame,
our approach performs space-time volumetric filtering, which:

Reduces temporal flickering

Ensures smooth fog evolution across frames

Preserves volumetric coherence in videos

📊 Evaluation

The method was evaluated against:

Homogeneous fog synthesis

2D noise-based non-homogeneous fog synthesis

Metrics

PSNR

SSIM

Lower PSNR/SSIM after dehazing indicates more realistic and challenging fog conditions,
where the proposed method consistently shows the lowest scores, confirming higher realism.

📁 Repository Structure 
.
├── src/
│   ├── volumetric_noise.py
│   ├── fft_filtering.py
│   ├── depth_transmission.py
│   ├── rendering.py
│   └── temporal_filter.py
├── examples/
│   ├── images/
│   └── videos/
├── README.md
└── requirements.txt

🧪 Usage
python synthesize_fog.py \
  --input input_video.mp4 \
  --depth depth_map.npy \
  --output output_video.mp4

📌 Applications

Synthetic data generation for adverse weather

Autonomous driving simulation

Computer vision robustness evaluation

Video-based environmental effects

Citation

If you use this work, please cite:

@article{depth3dfog2024,
  title={Depth-Aware 3D Fog Synthesis with Temporal Consistency},
  author={},
  journal={},
  year={2024}
}

📜 License

This repository is released for research and non-commercial use only,
in accordance with the paper’s publication license.

✉️ Contact

MinhoSeo (knut-Undergraduate researcher) https://itsukiseominho.github.io/Minhoseo.github.io/ , dat ngo (professiol)
