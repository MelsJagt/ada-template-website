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
        In this study a condensed version of Wikipedia is used <a href="https://snap.stanford.edu/data/wikispeedia.html">[4]</a>. Summary statistics can be found in <i><b>Table 1</b></i> above. We are interested in the individual players and more particularly in their unfinished paths. We would like to motivate players to succesfully complete multiple games, and for that we in the first place have to understand why some players are actually not even able to finish a game. <br><br>
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
<br />
<div style='background-color:#faefe1; border-left: solid #darkblue 4px; border-radius: 4px; padding:0.7em;'>
    <span style="color:black">
        Based on this result we can partition the players into 3 groups: <br><br>
        <ul>
            <li><b>1.</b> Players with <b>0</b> finished games. </li>
            <li><b>2.</b> Players with <b>partially</b> finished games. </li>
            <li><b>3.</b> Players with <b>only</b> finished games. </li>
        </ul> <br>
        Hence we observe that a substantial <b>25%</b> of the total number of players do not have any finished game at all&#128533; This is a big loss&#10071; Imagine if this portion would also have had succesful attemps (i.e. finished games). Then there would have been much more data on finished games to do further analysis on. On the other side of the spectrum we find that <b>51%</b> of the players have finished games only. We want to investigate what caused this bifurcation of behavior. The remaining <b>24%</b> falls in between these two categories. These players experience mixed results when playing the Wikispeedia game. <br><br>
        Let's have a look at the number of games played per group displayed in the <i><b>Figure 2</b></i> below.
    </span>
</div>
<br />
<p align="center">
    <img src="figures/fig2.jpg" width="700"/> 
</p>
<p align="center">
    <i ><b>Figure 2</b></i>
</p>
<div style='background-color:#faefe1; border-left: solid #darkblue 4px; border-radius: 4px; padding:0.7em;'>
    <span style="color:black">
        First we see that the distribution of the number of games played for all groups (i.e. <b>1.</b>, <b>2.</b> and <b>3.</b>) follows a power-law.  Other striking obervations are that group <b>1.</b> seems to play less games than the other two groups. Perhaps the fact that these players are not able to finish a single game at all demotivates them to play further. Group <b>2.</b> and <b>3.</b> are fairly similar, besides the few outliers in group <b>3.</b> These outlier represent a very tiny portion of highly motivated players that play many games.<br><br>
        Also we can check per player what type (i.e. finished or unfinished) their last game was. By definition group <b>1.</b> and <b>3.</b> only end on an unfinished or finished game respectively. It is interesting, however, to investigate group <b>2.</b>. We observe that players ending on an unfinished path have significantly less finished games overall compared to players ending on a finished path. This could suggest that players ending with an unsuccesful game could get demotivated to continue playing another game. This abandoning behavior could result in these players missing out on potential succesful games in the future.
    </span>
</div>
<br />

<div style='background-color:#08135c; border-left: solid #darkblue 4px; border-radius: 4px; padding:0.7em;'>
       <h2 style="color:white">Now what?</h2>
</div>
<div style='background-color:#faefe1; border-left: solid #darkblue 4px; border-radius: 4px; padding:0.7em;'>
    <span style="color:black">
        So we see many players that are unable to finish any game at all as they quickly abandon the game after relatively few games. On top of that there are players with mixed succes, though at some point they experience an unfinished path being the last straw that breaks the camel's back. Both groups are lost potential  &#10060;. Ideally we want these players to stay engaged in order to generate potential finished paths in the future &#128200;. One strategy to achieve this is to detect during an individual's progress when that person is likely to quit the game. When the odds for the latter are high, the game can offer "easier" games or provide "hints" to guide the player. <br><br>Hence, the first step to achieving this is to actually create an accurate detector. This is what we will address in this report. The aim is to build a simple (logistic regression) model using features that we can extract from two categories: <br><br>
        <ul>
        <li><b>Between game</b>: Features derived from the history of games played by a player.</li>
        <li><b>Im game</b>: Features derived from the path traversed of a single game of a player.</li>
        </ul> A schematic depiction of the overall model is depicted below in <i><b>Figure 3</b></i>. Accordingly we will train a classifier that predict wether the individual is likely to succesfully finish the game or not &#9989;. Under the assumption that players ending on a unfinished game get demotivated and are more likely to abandon the game, this investigation contributes to understanding why players quit the game. Concurrently, this provides the first stepping stone towards finding adequate means to keep players engaged in the game.
    </span>
</div>
<br />
<p align="center">
    <img src="figures/fig3.jpg" width="700"/> 
</p>
<p align="center">
    <i ><b>Figure 3</b></i>
</p>
