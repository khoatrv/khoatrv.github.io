---
layout: about
title: About
permalink: /
subtitle:

profile:
  align: right
  image: khoa.jpg
  image_circular: false # crops the image to make it circular

  more_info: >

[comment]: <> (    <p>555 your office number</p>)

[comment]: <> (    <p>123 your address street</p>)

[comment]: <> (    <p>Your City, State 12345</p>)

news: true # includes a list of news items
selected_papers: true # includes a list of papers marked as "selected={true}"
social: true # includes social icons at the bottom of the page
---

I’m a second-year PhD candidate in Computer Science at SKKU, advised by Prof. [Simon S. Woo](https://dash-lab.github.io/Professor). I earned my Bachelor's degree in Robotics Engineering from the Vietnam National University.

I’m always open to collaborations, discussions, and new opportunities. Feel free to reach out if you're interested in my research or would like to discuss potential projects.

**Research:** My research focuses on machine (un)learning, AI safety and physics AI.

<div markdown="1" style="position: relative;">

**1. Machine (un)learning.**
Understanding <span id="mu1" style="color: #e67e22">machine (un)learning</span> is still far behind its rapid application. What's wrong? Nothing. Science takes time, I believe in [slow-science](http://slow-science.org/). I enjoy exploring the fundamentals behind how models learn, forget, and retain knowledge.

**2. AI safety.**
I work on practical AI safety problems, particularly <span id="mu2" style="color: #e67e22">machine unlearning</span> and <span style="color: #2980b9">the detection of <span id="ai1" style="color: #2980b9">AI-generated</span> or manipulated content</span>.

**3. Physics AI.**
I am interested in how physics cues—such as motion, dynamics, and consistency—can help us better understand and <span id="ai2" style="color: #2980b9">detect AI-generated content</span>.

<svg id="mu-svg" style="position:absolute;top:0;left:0;width:100%;height:100%;overflow:visible;pointer-events:none;z-index:-1;opacity:0.4;" xmlns="http://www.w3.org/2000/svg">
  <defs>
    <marker id="mu-arr" markerWidth="8" markerHeight="6" refX="7" refY="3" orient="auto">
      <polygon points="0 0,8 3,0 6" fill="#e67e22"/>
    </marker>
    <marker id="mu-arr-start" markerWidth="8" markerHeight="6" refX="1" refY="3" orient="auto-start-reverse">
      <polygon points="0 0,8 3,0 6" fill="#e67e22"/>
    </marker>
    <marker id="ai-arr" markerWidth="8" markerHeight="6" refX="7" refY="3" orient="auto">
      <polygon points="0 0,8 3,0 6" fill="#2980b9"/>
    </marker>
    <marker id="ai-arr-start" markerWidth="8" markerHeight="6" refX="1" refY="3" orient="auto-start-reverse">
      <polygon points="0 0,8 3,0 6" fill="#2980b9"/>
    </marker>
  </defs>
  <line id="mu-line" stroke="#e67e22" stroke-width="2" marker-end="url(#mu-arr)" marker-start="url(#mu-arr-start)"/>
  <line id="ai-line" stroke="#2980b9" stroke-width="2" marker-end="url(#ai-arr)" marker-start="url(#ai-arr-start)"/>
</svg>

</div>

<script>
(function(){
  function drawArrow(id1,id2,lineId,svgId){
    var e1=document.getElementById(id1),e2=document.getElementById(id2),line=document.getElementById(lineId),svg=document.getElementById(svgId);
    if(!e1||!e2||!line||!svg)return;
    var wr=svg.parentElement.getBoundingClientRect(),r1=e1.getBoundingClientRect(),r2=e2.getBoundingClientRect();
    line.setAttribute('x1',r1.left-wr.left+r1.width/2);
    line.setAttribute('y1',r1.bottom-wr.top);
    line.setAttribute('x2',r2.left-wr.left+r2.width/2);
    line.setAttribute('y2',r2.top-wr.top-5);
  }
  function draw(){
    drawArrow('mu1','mu2','mu-line','mu-svg');
    drawArrow('ai1','ai2','ai-line','mu-svg');
  }
  if(document.readyState==='loading'){document.addEventListener('DOMContentLoaded',function(){setTimeout(draw,100)});}else{setTimeout(draw,100);}
  window.addEventListener('resize',draw);
})();
</script>

<!--
[comment]: <> (<details>)

[comment]: <> (<summary> <b> Research Summary</b></summary>)

[comment]: <> (<br>)

[comment]: <> (Fundamentally, my works considers the following aspects of the SW distance:)

[comment]: <> (<br>)

[comment]: <> (<br>)

[comment]: <> (<b> <i>Slicing distributions.</i></b> The vanilla sliced Wasserstein &#40;SW&#41; distance naively treats all one-dimensional projections the same and independently by using the uniform distribution over projecting directions. To improve and generalize the SW, I propose to search for the best distribution over projecting distributions &#40;or the slicing distribution&#41; which can maximize the expected projected distance. )

[comment]: <> (In particular, a regularized implicit family of distributions is introduced in <a href="https://arxiv.org/pdf/2002.07367.pdf">[ICLR'21]</a> and  explicit families &#40;von Mises-Fisher and Power Spherical&#41; are introduced in <a href="https://arxiv.org/pdf/2010.01787.pdf">[ICLR'21]</a>. Moreover, I introduce the usage of)

[comment]: <> (amortized optimization to predict the optimal slicing distribution given two input probability measures in the setting which has various pairs of probability measures in <a href="https://arxiv.org/pdf/2203.13417.pdf">[NeurIPS'22]</a> and <a href="https://arxiv.org/pdf/2301.04791.pdf">[ICML'23]</a>. To enhance further the quality of projecting directions, I break the independence between them by imposing the first order Markov structure in <a href="https://arxiv.org/pdf/2301.03749.pdf">[NeurIPS'23]</a>. )

[comment]: <> (To avoid unstable optimization and model misspecification in designing slicing model, I propose the energy-based slicing distribution  that is parameter-free and has the density proportional to an energy function of the projected one-dimensional Wasserstein distance in <a href="https://arxiv.org/pdf/2304.13586.pdf">[NeurIPS'23]</a>. To push forward further the optimization-free direction, I propose the random-path projecting direction in <a href="https://arxiv.org/pdf/2401.15889.pdf">[ICML'24]</a>.)

[comment]: <> (<br>)

[comment]: <> (<br>)

[comment]: <> (<b> <i>Projecting operators.</i></b> The vanilla sliced Wasserstein distance utilizes the Radon Transform as the projecting operator. The Radon Transform simply takes the inner product between the supports of a probability measure)

[comment]: <> (and  a projecting direction as the supports of the one-dimensional projected probability measure. To generalize the projecting operator to tensor spaces, I use the convolution operator to project probability measures over tensors to one-dimension in <a href="https://arxiv.org/pdf/2204.01188.pdf">[NeurIPS'22]</a>. In addition, I connect deep learning &#40;neural networks&#41; techniques to sliced Wasserstein by proposing Overaparameterized Radon Transform and Hierarchical Radon Transform in <a href="https://arxiv.org/pdf/2209.13570.pdf">[ICLR'23]</a>. Recently, I proposed hierarchical hybrid Radon Transform and hierarchical hybrid sliced Wasserstein distance for dealing with heterogeneous joint distributions in <a href="https://arxiv.org/pdf/2404.15378.pdf">[Arxiv'24]</a>.)

[comment]: <> (<br>)

[comment]: <> (<br>)

[comment]: <> (<b> <i>Numerical approximation.</i></b>  The SW distance is usually estimated by Monte Carlo integration due to the intractable expectation with respect to the slicing distribution. To reduce the variance of the Monte Carlo estimator,)

[comment]: <> (I first propose control variates which are based on the closed-form of the Wasserstein-2 distance between two Gaussians in <a href="https://arxiv.org/pdf/2305.00402.pdf">[ICLR'24]</a>. Importantly, the proposed control variates have linear time complexity and space complexity. In addition, I propose to use low-discrepancy sequences on the sphere &#40;Quasi-Monte Carlo&#41; to approximate sliced Wasserstein in <a href="https://arxiv.org/pdf/2309.11713.pdf">[ICLR'24]</a>. Moreover, we propose Randomized Quasi-sliced Wasserstein, an unbiased estimation of sliced Wasserstein which are based on randomizing low-discrepancy sequences.)

[comment]: <> (<br>)

[comment]: <> (<br>)

[comment]: <> (On the application side, my works  adopt optimal transport, Wasserstein distance, and sliced Wasserstein distance in point-clouds applications <a href="https://arxiv.org/pdf/2301.04791.pdf">[ICML'23]</a>, 3D mesh deformation <a href="https://arxiv.org/pdf/2305.17555.pdf">[ICLR'24]</a>, generative models &#40;GANs, Diffusion Models&#41; <a href="https://arxiv.org/pdf/2203.13417.pdf">[NeurIPS'22]</a> <a href="https://arxiv.org/pdf/2401.15889.pdf">[Arxiv'24]</a>, domain adaptation <a href="https://proceedings.mlr.press/v162/nguyen22d/nguyen22d.pdf">[ICML'22]</a>, <a href="https://proceedings.mlr.press/v162/nguyen22e/nguyen22e.pdf">[ICML'22]</a>, multimodal representation learning <a href="https://openreview.net/pdf?id=l60EM8md3t">[ICLR'24]</a>, 3D shape correspondence learning <a href="https://openreview.net/pdf?id=lz8a6ThNOi">[CVPR'24]</a>, and other tasks that need to deal with probability measures.)

[comment]: <> (</details>)

[comment]: <> (<br>) -->
