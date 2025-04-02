# 16825: Learning For 3D Vision
## Project 4 Results - Vinayak Patel (vinayakp)

### 1. 3D Gaussian Splatting
### 1.1. 3D Gaussian Rasterization
<p align="center">
    <figure style="display:inline-block; text-align:center; margin:10px;">
        <img src="website_results/Q1.1_and_1.2/q1_render.gif" width="768" height="256" />
        <figcaption>Rendering</figcaption>
    </figure>
</p>

### 1.2. Training 3D Gaussian Representations
<table>
 <tr>
  <th>Parameter</th>
  <th>Value</th>
 </tr>
 <tr>
  <td>Learning Rate : Opacities</td>
  <td>0.03</td>
 </tr>
 <tr>
  <td>Learning Rate : Scales</td>
  <td>0.01</td>
 </tr>
 <tr>
  <td>Learning Rate : Colours</td>
  <td>0.025</td>
 </tr>
  <tr>
  <td>Learning Rate : Means</td>
  <td>0.005</td>
 </tr>
  <tr>
  <td>PSNR</td>
  <td>27.780</td>
 </tr>
  <tr>
  <td>SSIM</td>
  <td>0.921</td>
 </tr>
</table>

<p align="center">
    <figure style="display:inline-block; text-align:center; margin:10px;">
        <img src="website_results/Q1.1_and_1.2/q1_training_final_renders.gif" width="768" height="256" />
        <figcaption>Final Rendering</figcaption>
    </figure>
</p>

<p align="center">
    <figure style="display:inline-block; text-align:center; margin:10px;">
        <img src="website_results/Q1.1_and_1.2/q1_training_progress.gif" width="768" height="256" />
        <figcaption>Training In Progress</figcaption>
    </figure>
</p>

### 1.3. Extensions
### 1.3.1 Rendering Using Spherical Harmonics
<p align="center">
    <figure style="display:inline-block; text-align:center; margin:10px;">
        <img src="website_results/Q1.1_and_1.2/q1_render.gif" width="768" />
        <figcaption>No Spherical Harmonics</figcaption>
    </figure>
</p>
<p align="center">
    <figure style="display:inline-block; text-align:center; margin:10px;">
        <img src="website_results/Q1.3/q1_render.gif" width="768" />
        <figcaption>With Spherical Harmonics</figcaption>
    </figure>
</p>

Views for Comparison
<table>
 <tr>
  <th>Frame Number</th>
  <th>Without Spherical Harmonics</th>
  <th>With Spherical Harmonics</th>
 </tr>
 <tr>
  <td>000</td>
  <td><img src="website_results/Q1.1_and_1.2/q1_render/000.png"/></td>
  <td><img src="website_results/Q1.3/q1_render/000.png"/></td>
 </tr>
 <tr>
  <td>013</td>
  <td><img src="website_results/Q1.1_and_1.2/q1_render/013.png"/></td>
  <td><img src="website_results/Q1.3/q1_render/013.png"/></td>
 </tr>
 <tr>
  <td>027</td>
  <td><img src="website_results/Q1.1_and_1.2/q1_render/027.png"/></td>
  <td><img src="website_results/Q1.3/q1_render/027.png"/></td>
 </tr>
</table>

<b>Differences:</b></br>
1. The reflections in the rendering with spherical harmonics are much more pronounced and realistic than compared to the regular rendering case without spherical harmonics. 
2. The rendering appears more realistic, with the lighting and shading information supplemented by the spherical harmonics. 
3. Even the colors are are more popping in the scene with spherical harmonics. It feels as if we turned on HDR and RTX On in a game such as Doom Eternal.

### 2. Diffusion-guided Opimization
### 2.1. SDS Loss + Image Optimization
Prompt: "a standing corgi dog"
<p align="center">
    <figure style="display:inline-block; text-align:center; margin:10px;">
        <img src="website_results/Q2.1/a_standing_corgi_dogwithout_guidance/output_a_iter_1500.png"/>
        <figcaption>Without Guidance : 1500 iterations</figcaption>
    </figure>
    <figure style="display:inline-block; text-align:center; margin:10px;">
        <img src="website_results/Q2.1/a_standing_corgi_dogwith_guidance/output.png"/>
        <figcaption>With Guidance : 2000 iterations</figcaption>
    </figure>
</p>
Prompt: "a hamburger"
<p align="center">
    <figure style="display:inline-block; text-align:center; margin:10px;">
        <img src="website_results/Q2.1/a_hamburgerhamburger_no_guidance/output_a_iter_400.png"/>
        <figcaption>Without Guidance : 400 iterations</figcaption>
    </figure>
    <figure style="display:inline-block; text-align:center; margin:10px;">
        <img src="website_results/Q2.1/a_hamburgerwith_guidance/output.png"/>
        <figcaption>With Guidance : 2000 iterations</figcaption>
    </figure>
</p>
Prompt: "the Forlorn from Dark Souls II Scholar of the First Sin"
<p align="center">
    <figure style="display:inline-block; text-align:center; margin:10px;">
        <img src="website_results/Q2.1/the_Forlorn_from_Dark_Souls_II_Scholar_of_the_First_Sin_without_guidance/output_t_iter_600.png"/>
        <figcaption>Without Guidance : 600 iterations</figcaption>
    </figure>
    <figure style="display:inline-block; text-align:center; margin:10px;">
        <img src="website_results/Q2.1/the_Forlorn_from_Dark_Souls_II_Scholar_of_the_First_Sin_with_guidance/output.png"/>
        <figcaption>With Guidance : 2000 iterations</figcaption>
    </figure>
</p>
Promt: "a photo of Tom Cruise winking"
<p align="center">
    <figure style="display:inline-block; text-align:center; margin:10px;">
        <img src="website_results/Q2.1/a_photo_of_Tom_Cruise_winking_without_guidance/output_a_iter_300.png"/>
        <figcaption>Without Guidance : 600 iterations</figcaption>
    </figure>
    <figure style="display:inline-block; text-align:center; margin:10px;">
        <img src="website_results/Q2.1/a_photo_of_Tom_Cruise_winking_with_guidance/output.png"/>
        <figcaption>With Guidance : 2000 iterations</figcaption>
    </figure>
</p>

### 2.2. Texture Map Optimization for Mesh
<p align="center"> 
    <figure style="display:inline-block; text-align:center; margin:10px;">
        <img src="website_results/Q2.2/Cow_with_black_and_white_spots_b_and_w_cow/output_C_iter_600.png"/>
        <figcaption>Prompt: "brown cow with green spots" 600 iterations</figcaption>
    </figure>
    <figure style="display:inline-block; text-align:center; margin:10px;">
        <img src="website_results/Q2.2/Cow_with_Cheetah_pattern_having_black_sponts_and_yellow_colorcheetah_cow_black_yellow/output_C_iter_600.png"/>
        <figcaption>   Prompt: "cow with cheetah pattern having black and yellow color" 600 iterations</figcaption>
    </figure>
</p>

### 2.3. NeRF Optimization
<table>
 <tr>
  <th>Parameter</th>
  <th>Value</th>
 </tr>
 <tr>
  <td>lambda_entropy</td>
  <td>0.00001</td>
 </tr>
 <tr>
  <td>lambda_iter_ratio</td>
  <td>0.001</td>
 </tr>
 <tr>
  <td>lambda_orient</td>
  <td>0.001</td>
 </tr>
  <tr>
  <td>Iterations</td>
  <td>5000</td>
 </tr>
</table>

I tried a few prompts but I was not able to get good results for this part. I was always getting white noise at the end.

### 2.4. Extensions
### 2.4.1. View-dependent texture embedding
<video width="256" height="256" controls>
  <source src="website_results/videos/depth_ep_40.mp4" type="video/mp4">
</video> 
<video width="256" height="256" controls>
  <source src="website_results/videos/rgb_ep_40.mp4" type="video/mp4">
</video>


https://github.com/user-attachments/assets/f76ba9c3-c45e-4439-a312-577b774a0f8a

https://github.com/user-attachments/assets/3b90b733-1141-49ff-bada-8eaa70e38cd3

After 40 epochs. Top one is depth. Bottom one is RGB



