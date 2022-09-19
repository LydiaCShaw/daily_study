---
layout: post
read_time: true
show_date: true
title: Construction and validation of a three-dimensional finite element model
date:  2022-09-19 17:00:21 -0600
description:  Construction and validation of a three-dimensional finite element model
img: posts/stock/LR.jpg
tags: [FEM Model, Off-set, Facet Joint, Firction Coefficient Ligamanets, Validation, Mechanical Peoperties in silico]
author: Lydia Shaw
github:  LydiaCShaw
mathjax: yes
---

# Construction and validation of a three-dimensional finite element model of degenerative scoliosis

Zheng et al. Journal of Orthopaedic Surgery and Research (2015) 10:189 
DOI 10.1186/s13018-015-0334-1

## **Off-set**

The solid model of each vertebra was divided into a high-quality mesh using the self-adapting dynamic biomechanical finite element grid of the Modeler. The length of the mesh was designated as 2 mm. The surface elements of each vertebral body were selected (except for the facet joint and intervertebral disc) using the submodel design tools of the Modeler and were used to form shell elements with an average thickness of **1.2 mm to represent the cortical bone.**

# Model

The lamina terminalis of the **intervertebral disc** was simulated with **1-mm shell elements**, and the **nucleus pulposus was simulated as an incompressible viscoelastic liquid**. 

The annulus fibrosus was modeled as groundmass with collagen fiber buried within it. The groundmass was constituted with three-tier continuous rings, and the collagen fiber was constituted with eight-tier cord elements only bearing tensile stress. The collagen fibers were arranged as scissors in the rings, and the included angle with the surface of the intervertebral disc was ±30° on average.

# Facet Joint and Coefficient

Using the graphical interactive modeling tools of the Modeler, the cartilage of each facet joint of each vertebra was swept outwards to form a one-tier 0.6-mm mesh as the cartilage of facet joint, which was simulated as a surface-tosurface contact element with its primary interval of 0.5 mm and with a friction coefficient of 0.1.

# Ligaments

Using the graphical interactive modeling tools of the Modeler, the anatomical positions of the main ligaments of the lumbar segment were accurately selected, and the ligaments were simulated with cord elements, including the anterior longitudinal ligament, the posterior longitudinal ligament, the supraspinous ligament, the interspinous ligament, the ligamentum flavum, the intertransverse ligament, and the capsular ligament of the facet joint. The texture parameter of each ligament was defined as nonlinear as shown in this article

# Validation

## Geometric validation

The finite element model of DS was contrasted to the patient’s X-ray plate to validate the model’sgeometric similarity according to their coincidence. The indexes of testing included **coronal Cobb angle and lumbar lordosis angle.**

## Experimental validation

The surface of the L1 vertebral body was loaded to 10 Nm in 10 substeps in nodal load mode. The model was loaded in flexion, extension, left lateral bending, right lateral bending, left rotation, and right rotation, and the calculated results were compared with the experimental results of the elderly population in the in vitro experiment conducted by Chen et al.