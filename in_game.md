---
layout: default
---

<div style='background-color:#08135c; border-left: solid #darkblue 4px; border-radius: 4px; padding:0.7em;'>
       <h2 style="color:white">2. In game</h2>
</div>
<div style='background-color:#faefe1; border-left: solid #darkblue 4px; border-radius: 4px; padding:0.7em;'>
    <span style="color:black">
        After having made an analysis based on players history, we now focus on the analysis per game and try to understand what makes a player finish or not. We first focus on the Wikipedia page categories to see if players get stuck in certain ones, and if the starting or the target page has an impact on the success of the game. Then we focus on the paths and try to find out the relationship between the path the player took, the distance to the target and the result of the game, as well as the motivation to keep playing.
    </span>
</div><br /><br />

<div style='background-color:#08135c; border-left: solid #darkblue 4px; border-radius: 4px; padding:0.7em;'>
       <h2 style="color:white">2.1 Analysis on categories.</h2>
</div>
<div style='background-color:#faefe1; border-left: solid #darkblue 4px; border-radius: 4px; padding:0.7em;'>
    <span style="color:black">
        We want to analyze where the player can get stuck during their games as this could potentially lead to an unfinished result. For each Wikipedia article in the players graph (i.e. that path taken during a game), we have its in and out degree and these two values are not always the same. In fact when we constructed  the graph we remove edges that went back to the previous pages visited. For example, suppose a player starts with page A and then goes to B. He/she might then see that it was not a good idea to go to B and uses the back button to return to A, after which the player moves go to C. At the end A has in/out degree of 0/2 whereas B has in/out degree 1/0. Therefore, analysising the difference between the degrees can give us insight on where player get stuck. <br><br>
        In fact when we compute <code class='python'>D = in_deg - out_degree</code>, we can have two cases:<br><br>
        <ul>
        <li><b><code class='python'>D</code> is big</b>: we came to this node (wikipedia page) but then returned to the previous one - the player thought that he/she was on the wrong way (node B in our example)</li>
        <li><b><code class='python'>D</code> is negative</b>: this means that we get back and forth from this node, not knowing how to escape - the player think he is at a key node but does not know how to go further (node A in our example)</li>
        </ul>
        \begin{displaymath} y=
    </span>
</div>