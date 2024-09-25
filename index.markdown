---
layout: home
title: EMO-Harmonizer
description: Emotion-Driven Melody Harmonization via Melodic Variation and Functional Representation
github_link: https://github.com/Yuer867/EMO_Harmonizer
---

## Introduction

In this paper, we propose a novel **functional representation** designed as an alternative to [REMI](https://github.com/YatingMusic/remi), 
a popular event representation that uses note pitch values and chord names to encode symbolic music.testttt!!

<div align="center">
  <img src="../figures/emo_harmonizer/representation.png" width=500 alt="">
  <figcaption><strong>Fig.1</strong> Illustration of (a) REMI and (b) the proposed functional
representation, differing in note pitch and chord name events.</figcaption>
</div>

This new method takes **musical keys** into account, 
recognizing their significant role in shaping music’s emotional character through major-minor tonality. 

<div align="center">
  <img src="../figures/emo_harmonizer/key_distribution.png" width=500 alt="">
  <figcaption><strong>Fig.2</strong> Key histogram of high/low valence clips from EMOPIA.</figcaption>
</div>

Specifically, our method represents both melody notes and chords with Roman numerals relative to musical keys, 
a **functional format** considering the relationships between notes, chords and scales (major or minor). 

<div align="center">
  <img src="../figures/emo_harmonizer/switch.png" width=400 alt="">
  <figcaption><strong>Fig.3</strong> Illustration of the conversion between letters and Roman numerals in the cases of C major / c minor. The solid line represents a direct one-to-one conversion, while the dotted line stands for a random conversion to either one of them.</figcaption>
</div>

It also allows for melodic variation with respect to keys and addresses the problem of data scarcity for better emotion modeling. 

A Transformer is employed to harmonize key-adaptable melodies, allowing for keys determined in rule-based or model-based manner.

## Harmonization Samples

We present a selection of samples within the same context as our user study, i.e., 
**original** pieces as well as their four variants generated with the same melody but the opposite emotion condition. Four variants include:
* **REMI (trans)**: transpose to C major / c minor and represent in REMI; simply set the emotion event to
the target emotion without changing keys
* **REMI (rule)**: transpose to C major / c minor and represent in REMI; determine keys in rule-based method
* **Ours (rule)**: represent in functional representation; determine keys in rule-based method
* **Ours (model)**: represent in functional representation; determine keys in model-based method


### Illustration

<div align="center">
  <img src="../figures/emo_harmonizer/demo.png" width=700 alt="">
  <figcaption><strong>Fig.4</strong> Illustration of a re-harmonization example using the method "Ours (rule)". 
Top: original melody and chord progression from the validation set conveying positive emotion. 
Bottom: melodic variation with re-harmonized chord progression to convey negative emotion. 
The downward arrows in the bottom figure indicate the notes shifting down by semitones due to a key change from E major to e minor. 
This illustration is not an exact match with the following audio for improved clarity in layout. </figcaption>
</div>

<table class="audio-table">
  <thead>
    <tr class="header">
    <th>Original (Positive)</th>
    <th>Generated (Negative)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q1_biROWEwkDQQ_3/Q1_biROWEwkDQQ_3.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q1_biROWEwkDQQ_3/relative_switch.wav" type="audio/mpeg" /></audio></td>
    </tr>
  </tbody>
</table>


### Negative Variants for Positive Original Pieces

<table class="audio-table">
  <thead>
    <tr class="header">
    <th></th>
    <th>Original</th>
    <th>REMI (trans)</th>
    <th>REMI (rule)</th>
    <th>Ours (rule)</th>
    <th>Ours (model)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Sample#1</td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q1__SJQaaRzD-A_0/Q1__SJQaaRzD-A_0.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q1__SJQaaRzD-A_0/transpose.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q1__SJQaaRzD-A_0/transpose_switch.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q1__SJQaaRzD-A_0/relative_switch.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q1__SJQaaRzD-A_0/relative_begin.wav" type="audio/mpeg" /></audio></td>
    </tr>
    <tr>
      <td>Sample#2</td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q1_mX-xs3OVhTs_0/Q1_mX-xs3OVhTs_0.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q1_mX-xs3OVhTs_0/transpose.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q1_mX-xs3OVhTs_0/transpose_switch.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q1_mX-xs3OVhTs_0/relative_switch.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q1_mX-xs3OVhTs_0/relative_begin.wav" type="audio/mpeg" /></audio></td>
    </tr>
    <tr>
      <td>Sample#3</td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q1_s5b8viFsVJE_2/Q1_s5b8viFsVJE_2.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q1_s5b8viFsVJE_2/transpose.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q1_s5b8viFsVJE_2/transpose_switch.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q1_s5b8viFsVJE_2/relative_switch.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q1_s5b8viFsVJE_2/relative_begin.wav" type="audio/mpeg" /></audio></td>
    </tr>
    <tr>
      <td>Sample#4</td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q4_22S3w4idugs_0/Q4_22S3w4idugs_0.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q4_22S3w4idugs_0/transpose.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q4_22S3w4idugs_0/transpose_switch.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q4_22S3w4idugs_0/relative_switch.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q4_22S3w4idugs_0/relative_begin.wav" type="audio/mpeg" /></audio></td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <td>Sample#5</td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q4_cXxGBDgFCs8_0/Q4_cXxGBDgFCs8_0.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q4_cXxGBDgFCs8_0/transpose.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q4_cXxGBDgFCs8_0/transpose_switch.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q4_cXxGBDgFCs8_0/relative_switch.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q4_cXxGBDgFCs8_0/relative_begin.wav" type="audio/mpeg" /></audio></td>
    </tr>
  </tfoot>
</table>


### Positive Variants for Negative Original Pieces

<table class="audio-table">
  <thead>
    <tr class="header">
    <th></th>
    <th>Original</th>
    <th>REMI (trans)</th>
    <th>REMI (rule)</th>
    <th>Ours (rule)</th>
    <th>Ours (model)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Sample#1</td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q3_fuCxYrru2S4_0/Q3_fuCxYrru2S4_0.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q3_fuCxYrru2S4_0/transpose.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q3_fuCxYrru2S4_0/transpose_switch.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q3_fuCxYrru2S4_0/relative_switch.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q3_fuCxYrru2S4_0/relative_begin.wav" type="audio/mpeg" /></audio></td>
    </tr>
    <tr>
      <td>Sample#2</td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q3_ii1Jw1-7Ka4_2/Q3_ii1Jw1-7Ka4_2.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q3_ii1Jw1-7Ka4_2/transpose.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q3_ii1Jw1-7Ka4_2/transpose_switch.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q3_ii1Jw1-7Ka4_2/relative_switch.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q3_ii1Jw1-7Ka4_2/relative_begin.wav" type="audio/mpeg" /></audio></td>
    </tr>
    <tr>
      <td>Sample#3</td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q2_0v2N1ROvEI0_1/Q2_0v2N1ROvEI0_1.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q2_0v2N1ROvEI0_1/transpose.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q2_0v2N1ROvEI0_1/transpose_switch.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q2_0v2N1ROvEI0_1/relative_switch.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q2_0v2N1ROvEI0_1/relative_begin.wav" type="audio/mpeg" /></audio></td>
    </tr>
    <tr>
      <td>Sample#4</td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q2_5CEAeMiXKaA_0/Q2_5CEAeMiXKaA_0.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q2_5CEAeMiXKaA_0/transpose.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q2_5CEAeMiXKaA_0/transpose_switch.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q2_5CEAeMiXKaA_0/relative_switch.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q2_5CEAeMiXKaA_0/relative_begin.wav" type="audio/mpeg" /></audio></td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <td>Sample#5</td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q2_jIKX3ShvLxo_2/Q2_jIKX3ShvLxo_2.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q2_jIKX3ShvLxo_2/transpose.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q2_jIKX3ShvLxo_2/transpose_switch.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q2_jIKX3ShvLxo_2/relative_switch.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q2_jIKX3ShvLxo_2/relative_begin.wav" type="audio/mpeg" /></audio></td>
    </tr>
  </tfoot>
</table>

## Authors and Affiliations

* Jingyue Huang  
Research Assistant @ National Taiwan University / PhD student @ UC San Diego  
jih150@ucsd.edu  
 
* Yi-Hsuan Yang  
Professor @ National Taiwan University / Joint-Appointed Researcher @ Academia Sinica  
yhyangtw@ntu.edu.tw, affige@gmail.com  
[website](https://affige.github.io/)

[jekyll-organization]: https://github.com/jekyll
