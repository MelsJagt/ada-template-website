<div style='background-color:#08135c; border-left: solid #darkblue 4px; border-radius: 4px; padding:0.7em;'>
       <h2 style="color:white">Interlude</h2>
</div>
<div style='background-color:#faefe1; border-left: solid #darkblue 4px; border-radius: 4px; padding:0.7em;'>
    <span style="color:black">
        Wikispeedia is an online human-computation game based on Wikipedia <a href="https://dlab.epfl.ch/wikispeedia/play/">[1]</a>. A player has to navigate from a designated source to a given target article, solely by clicking on Wikipedia links. As such, this generates a dataset that contains human navigation paths on Wikipedia which allows for interesting studies. That is, topics concerning the semantic distance between concepts <a href="http://infolab.stanford.edu/~west1/pubs/West-Pineau-Precup_IJCAI-09.pdf">[2]</a> or the searching behavior of humans <a href="http://infolab.stanford.edu/~west1/pubs/West-Leskovec_WWW-12.pdf">[3]</a> can be interrogated. To do this, a lot of data is needed which can be supported by an active community that frequently plays the Wikispeedia game.  But how can you get people to play and finish the game maybe even multiple times? What motivates people to finish the task and do not give up? With this work these questions are answered by proposing a set-up for the game that is likely to incentivize people to stay engaged, and hence more data for analysis purposes can be generated.
    </span>
</div>
<br />
<p align="center">
    <img src="figures/data_statistics.jpg" width="500"/> 
</p>
<p align="center">
    <i ><b>Table 1</b></i>
</p>
<br />
<div style='background-color:#08135c; border-left: solid #darkblue 4px; border-radius: 4px; padding:0.7em;'>
       <h2 style="color:white">Data</h2>
</div>
<div style='background-color:#faefe1; border-left: solid #darkblue 4px; border-radius: 4px; padding:0.7em;'>
    <span style="color:black">
        In this study a condensed version of Wikipedia is used <a href="https://snap.stanford.edu/data/wikispeedia.html">[4]</a>. Summary statistics can be found in <i><b>Table 1</b></i> above. We are interested in the individual players and more particularly in their unfinished paths. As we would like to motivate players to succesfully complete multiple games, we in the first place have to understand why some players are actually not able to finish a game. <br><br>
        For each unique player we can compute the proportion of finished games over the total number of games played by that person. The distribution of the latter is displayed in <i><b>Figure 1</b></i> below.
    </span>
</div>
<br />
<p align="center">
    <img src="figures/fig1.jpg" width="500"/> 
</p>
<p align="center">
    <i ><b>Figure 1</b></i>
</p>


