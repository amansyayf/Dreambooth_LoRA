# Dreambooth_LoRA
## About
Repository of fine-tuning of deffusion model using LoRA. Process is based on [DreamBooth](https://arxiv.org/abs/2208.12242) paper.
## Annotation
The article discribes fine-tuning technique of text-to-image model having just a few images of subject. This efficient technique allows to reproduce subject in different conditions and preserve semantic class knowledge.
Dreambooth solves two main problems: overfitting and language drift. In the article, the authors present two key methods: Class-specific Prior Preservation Loss and Rare-token Indentifier. Class-specific Prior Preservation Loss allows to preserve initial knowledge about specific classes. Rare-token Indentifier (e.g. "sks") is special identifier of subject that allows to "implant" subject into model vocabulary. 
As a result giving a prompt with chosen token identifier model output unique image preserving the subject instance features. There many possibilities to the modification of a subject instance, some of these include drawing a subject in a different place, color modification, drawing the subject from a different angle and art renditions.


## Experiments
## Prior Preservation Loss 
Check in practice the important of this Loss. Indeed it seems preventing from overfitting and bringing diversity in pictures, when we have unusual prompts. But without using it better for betraying subject features. 
Columns represents seeds, [1000000, 2000000, 3000000, 4000000, 5000000] starting from the left

> Without Prior Loss
<!-- #region -->
<p align="center">
<img  src="contents/without_pLoss.jpg">
</p>
<!-- #endregion -->

> With Prior Loss
<!-- #region -->
<p align="center">
<img  src="contents/base.jpg">
</p>
<!-- #endregion -->

## Learning Rate and number of training steps
Fine-tuning with all hyperparameters equal across runs, exept LR, number of training steps.  In our case (lr=1e-4, steps=2500) or (lr=5e-4, steps=1500) seems better. With forth prompth model have failure, probably due to low probability of co-occurrence in the initial training set and overfitting. 
Columns of pictures represent training steps, [500, 1000, 1500, 2000, 2500] starting from the left. Seed = 2000000.

> Lr=5e-5
<!-- #region -->
<p align="center">
<img  src="contents/5e-5.jpg">
</p>
<!-- #endregion -->

> Lr=1e-4
<!-- #region -->
<p align="center">
<img  src="contents/1e-4 (1).jpg">
</p>
<!-- #endregion -->

> Lr=5e-4
<!-- #region -->
<p align="center">
<img  src="contents/5e-4 (1).jpg">
</p>
<!-- #endregion -->

## LORA rank
Here it can be seen that as the rank increases, the quality increases. However with it the use of memory and training parameters abruptly increases.
 
Columns of pictures represent seeds [1000, 2000, 3000, 4000] starting from the left.

> rank=1
<!-- #region -->
<p align="center">
<img  src="contents/1.jpg">
</p>
<!-- #endregion -->

> rank=2
<!-- #region -->
<p align="center">
<img  src="contents/2.jpg">
</p>
<!-- #endregion -->

> rank=4
<!-- #region -->
<p align="center">
<img  src="contents/4.jpg">
</p>
<!-- #endregion -->

> rank=6
<!-- #region -->
<p align="center">
<img  src="contents/6.jpg">
</p>
<!-- #endregion -->

