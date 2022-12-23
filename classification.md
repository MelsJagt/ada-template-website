---
layout: default
---

<div style='background-color:#08135c; border-left: solid #darkblue 4px; border-radius: 4px; padding:0.7em;'>
       <h2 style="color:white">3. Classification</h2>
</div>
<div style='background-color:#faefe1; border-left: solid #darkblue 4px; border-radius: 4px; padding:0.7em;'>
    <span style="color:black">
        Here we perform a simple logistic regression to predict the classes finished or unfinished based on the features extracted in the between game and in game analysis. 
    </span>
</div><br /><br />

<div style='background-color:#08135c; border-left: solid #darkblue 4px; border-radius: 4px; padding:0.7em;'>
       <h2 style="color:white">3.1 Performance</h2>
</div>
<div style='background-color:#faefe1; border-left: solid #darkblue 4px; border-radius: 4px; padding:0.7em;'>
    <span style="color:black">
        A 10-fold cross validation is performed to asses the performance of the logistic regression model along. More specifically we compute the following metric: precision, recall, accuracy and f-score. <i><b>Figure</b></i> Below displays the results.
    </span>
</div>
<br />
<p align="center">
    <img src="figures/fig15.jpg" width="500"/> 
</p>
<p align="center">
    <i ><b>Figure 15</b></i>
</p>
<div style='background-color:#faefe1; border-left: solid #darkblue 4px; border-radius: 4px; padding:0.7em;'>
    <span style="color:black">
        We can interpret these results as follows:<br><br>
        <ul>
        <li><b>precision</b> : The fraction (<b>0.70</b>) of a predicted finished games that are actually finished by the player.</li>
        <li><b>recall</b> : The fraction (<b>0.81</b>) actual finished games that are predicted as finished by the model.</li>
        <li><b>accuracy</b> : The total fraction of correctly predicted classes</li>
        <li><b>f1</b> : The harmonic mean of precision and recall.</li>
        </ul>
        These results are dependent on the the decision threshold of 0.5. That is, we predict the game to be finished for values larger then 0.5. Similarly we predict unfinished games for values smaller than 0.5. In addition, we computed the ROC AUC curve (<i><b>Figure 16</b></i>) as this is independent on the choice of threshold (unlike accuracy, precision, recall and f1).
    </span>
</div>
<br />
<p align="center">
    <img src="figures/fig16.jpg" width="500"/> 
</p>
<p align="center">
    <i ><b>Figure 16</b></i>
</p>
<div style='background-color:#faefe1; border-left: solid #darkblue 4px; border-radius: 4px; padding:0.7em;'>
    <span style="color:black">
        We observe the AUC of 0.73 which is considered acceptable for a classifier <a href="https://www.jto.org/article/S1556-0864(15)30604-3/fulltext">[5]</a>
    </span>
</div>