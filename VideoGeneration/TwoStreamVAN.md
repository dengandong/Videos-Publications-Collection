Video generation is an inherently challenging task, as it
requires modeling realistic temporal dynamics as well as
spatial content. Existing methods entangle the two intrinsically
different tasks of motion and content creation in a
single generator network, but this approach struggles to simultaneously
generate plausible motion and content. To improve
motion modeling in video generation task, we propose
a two-stream model that disentangles motion generation
from content generation, called a Two-Stream Variational
Adversarial Network (TwoStreamVAN). Given an action
label and a noise vector, our model is able to create
clear and consistent motion, and thus yields photorealistic
videos. The key idea is to progressively generate and
fuse multi-scale motion with its corresponding spatial content.
Our model significantly outperforms existing methods
on the standard Weizmann Human Action, MUG Facial Expression
and VoxCeleb datasets, as well as our new dataset
of diverse human actions with challenging and complex motion.
