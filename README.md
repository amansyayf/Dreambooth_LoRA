# Dreambooth_LoRA
## About
Repository of fine-tuning of deffusion model using LoRA. Process is based on [DreamBooth](https://arxiv.org/abs/2208.12242) paper.
## Annotation
The article discribes fine-tuning technique of text-to-image model having just a few images of subject. This efficient technique allows to reproduce subject in different conditions and preserve semantic class knowledge.
Dreambooth solves two main problems: overfitting and language drift. In the article, the authors present two key methods: Class-specific Prior Preservation Loss and Rare-token Indentifier. Class-specific Prior Preservation Loss allows to preserve initial knowledge about specific classes. Rare-token Indentifier is special identifier of subject that allows to "implant" subject into model vocabulary. 
As a result giving a prompt with chosen token identifier model output unique image preserving the subject instance features. There many possibilities to the modification of a subject instance, some of these include drawing a subject in a different place, color modification, drawing the subject from a different angle and art renditions.
