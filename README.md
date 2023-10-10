<h1 align="center">Detecting_Dogwhistles</h1>
<h3 align="center">Evolution in the Detection of Online Hate</h3>

This project aimed to create a machine learning model that could identify hateful comments when slurs had been replaced by covert Dogwhistles.

<h3 aligh="left">What is a Dogwhistle?</h3>

A Dogwhistle is an encoded word or phrase that simultaneously conveys one meaning to a broad audience and a second, hateful, meaning to a narrow in-group.

These are used to evade both political repercussions and algorithmic content moderation.

<h3 aligh="left">Data Generation</h3>

Acquiring the data to train the models was always going to be a challenge due to the difficultly of finding real-life examples and the ethical concerns relating to the generation of such content by Generative AI.

After various tests, it was decided that the best way to get this data was to generate it using templates found at HateCheck, which is used to test AI content moderation models.

Direct slurs were replaced by their Dogwhistle counterparts, and the data was upsampled to ensure there were no class imbalances and then processed for model training.

<h3 aligh="left">Comparing Models</h3>

| Metric | Logistic Regression | Perceptron | MLP |
| ------ | ------------------- | ---------- | --- |
| Accuracy | 0.9770 | 0.9679 | 0.9721 |
| Precision | 0.9800 | 0.9725 | 0.9696 |
| Recall | 0.9882 | 0.9833 | 0.9924 |
| F1 | 0.9841 | 0.9779 | 0.9808 |

<h3 aligh="left">Custom Data</h3>


| Text | Target | Log Reg Probability | Log Reg Prediction | MLP Probability | MLP Prediction | Perceptron Decision | Perceptron Prediction |
| ---- | ------ | ----------- | ---------- | ----------- | ---------- | ----------- | ---------- |
| obama is another deadbeat dad | 1 | 0.89698 | 1 | 1.00000 | 1 | 0.77307 | 1 |
| another example of the dangerous impact of the genderist agenda on our children | 1 | 0.78898 | 1 | 0.00009 | 0 | -0.05762 | 0 |
| our streets are now overrun with dindus | 1 | 0.88994 | 1 | 1.00000 | 1 | 0.57793 | 1 |
| the demographic of my small town is now what you might call urban | 1 | 0.10620 | 0 | 0.63762 | 1 | 0.30551 | 1 |
<h3 aligh="left">Conclusions</h3>
