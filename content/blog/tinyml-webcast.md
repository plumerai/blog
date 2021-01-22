---
title: "tinyML Talks: Binarized Neural Networks on microcontrollers"
subtitle: "Running Binarized Neural Networks on microcontrollers"
heroImage: ""
date: 2021-01-22T12:09:02+01:00
draft: false
socialTitle: "tinyML Talks: Binarized Neural Networks on microcontrollers"
socialDescription: "Running Binarized Neural Networks on microcontrollers"
socialImage: "/images/tinyml/hero-image.png"
---

For the past few months we have been working very hard on something new: Binarized Neural Networks on microcontrollers. By bringing deep learning to cheap, low-power microcontrollers we remove price and energy barriers and make it possible to embed AI into basically any device, even for relatively complex tasks such as person detection.

This week, we gave a presentation as part of the tinyML Talks webcast series where we explained what we had to build to make this work. We demonstrated how combining our custom training algorithms, inference software stack and datasets results in a highly accurate and efficient solution - in this case for person presence detection on the STM32L4R9, an ARM Cortex-M4 microcontroller from STMicroelectronics. This technology can be implemented to trigger push notifications for smart home cameras, wake up devices when a person is detected, detect occupancy of meeting rooms and for many more applications. This is a step towards our goal of making deep learning ultra low-power and a future where battery-powered peel-and-stick sensors can perform complex AI tasks everywhere.

{{< youtube f9SNqDejOB0 >}}

Our BNN models with our proprietary inference software are faster and more accurate on ARM Cortex-M4 microcontrollers than the best publicly available 8-bit deep learning models with TensorFlow Lite for Microcontrollers.

{{< figure src="/images/tinyml/cortex-m4-hero.svg" >}}

We quickly found out that great training algorithms and inference software are not enough when building a solution for the real world. Collecting and labeling our own data turned out to be crucial in dealing with a wide variety of difficulties.

{{< rawhtml >}}
  <video preload="auto" autoplay loop muted width="100%" poster="/images/tinyml/slide-real-world.png" class="html-video">
    <source src="/images/tinyml/slide-real-world.mp4" type="video/mp4" }}>
    </video>
{{< /rawhtml >}}

Testing our models thoroughly is equally as important. Instead of relying only on simplistic metrics such as accuracy, we developed a suite of unit tests to ensure reliable performance in a wide variety of settings.

![Unit tests for Deep Learning Applications](/images/tinyml/slide-dl-unittests.png)

Bringing all of this together results in a highly robust and efficient solution for person presence detection, as we showed in our [live demo](https://youtu.be/f9SNqDejOB0?t=2556).

![Live Demo of Person Detection running on Cortex-M4 microcontroller](/images/tinyml/demo.png).

We're just scratching the surface with person detection and we have a lot more in store for the coming months - more applications on Arm Cortex-M microcontrollers, and even better performance with our own IP-core for BNN inference on low-powered FPGAs and with the xcore.ai platform from XMOS.

![What's Next?](/images/tinyml/slide-whats-next.png)

We are very happy with the high attendance during the live webcast and a ton of questions were submitted during the Q&A. There was no time to answer all of them live, so we shared our answers on the [tinyML forum](https://forums.tinyml.org/t/tinyml-talks-on-january-19-2021-running-binarized-neural-networks-on-microcontrollers-by-lukas-geiger/485) and we’ll be sharing more of our progress at the tinyML Summit in March.

If you’re thinking about using Binarized Neural Networks to enable highly accurate deep learning on microcontrollers, get in touch!
