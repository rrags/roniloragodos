# (Modular) Synthesis Techniques #1 - Sequence Mixing

[Midwest Modular](/assets/modular.JPG)

<i>Last updated 5/2/24</i>

This past week I had the pleasure of attending the POMS (Production and Operations Management Society) conference in Minneapolis, MN. I presented my ongoing joint work with Dr. Tong Wang, Dr. Jeffrey Hu, and Lu Feng <i>The Risk of Inferring Data Insights from Post-Hoc Explanations of Machine Learning Models</i>, which is essentially a polemic against post-hoc explainers. I'll probably write a post about this work once we put a pre-print online. 

It was a happy coincidence that the conference was in Minneapolis because Minneapolis is home to <i>Midwest Modular</i>, a store specializing in modular synthesizer equipment that I have been meaning to make the trip to since 2019. And I am so happy I got to go because I had the best experience at a music store that I have ever had there! For this reason, I want to recount my trip in this post and share some of what I learned at the store. 

------

<i>If you're not familiar, modular synthesizers are basically adult legos for musicians. If you are interested in getting into modular synths, I suggest first testing the waters by toying around with [VCV Rack](https://vcvrack.com/</i>), a FOSS (Free Open Source Software) eurorack simulator. The  remainder of this post is going to be heavy with synth jargon. </i>

------

From my perspective, music stores can be scary and intimidating places. Especially as a beginning guitar player, I remember being even nervous to touch any equipment at a music store let alone play something so that the staff and customers might hear how inexperienced I was. However, the store attendant (owner?) at Midwest modular, Joe, made me feel very comfortable and was very excited to share his knowledge of synthesis and synthesizers with me. I expected my trip to be maybe 20 minutes tops where I went to try out and subsequently purchase an oscillator, but it turned into a full fledged 2-hour impromptu lesson on the theory of synthesis and use of modular synthesizers! Joe, who has a degree in Synthesis from Berkely taught me, through use of waveform diagrams on post-it notes and example patches: core concepts about filters, FM synthesis, mixing, sequencing, slew limiters, wavefolding, the utility of random sources, and how to use a VCO+Wavefolder as an oscilloscope. Additionally, he shared information about the history of the development of synthesizers, recalling the stories of Moog and Buchla and the techniques of east and west coast synthesis. He also shared many patch ideas with me that I could use as part of my stated goal to make Berlin school music, one of which I will describe below. 

Many modular sequencers have only 4-8 steps, and as you can imagine it can be difficult to make interesting sounding music with 4-8 steps. You would only really be able play a piece that consists of 1 measure that loops endlessly. With 2 8-step sequencers, a mixer, and a quantizer, this problem can be avoided. 

The basic idea is to 

- run two sequences A and B with coprime step lengths M and N, respectively
- mix the CV outputs of the sequences
- run the output of the mixer into a quantizer
- run the quantized, mixed, sequence into your favorite VCO

Since M and N are different, the mixed sequence will have a length of MN (as M and N are coprime, their least common multiple is MN). See the visualizations below for some intuition.

[Sequence A](/assets/sq-figure0-1.png)

Above, we have sequence A which is a 2-note ascending sequence. 

[Sequence B](/assets/sq-figure1-1.png)

Above, we have sequence B which is a 3-note sequence which goes up and down. 2 and 3 only have 1 as a common divisor, so they are coprime. Played in unison and mixed, we get the following equivalent 6 step sequence.

[Sequence A+B](/assets/sq-figure0-1.png)

Sequence A+B (black) is the sum of the component sequences. Note how varied the voltages are for each of the steps!



<i>Bonus:</i>

In the above example, I implicitly assumed that the two sequencers were running at the same clock speed. This way, you get maximum complexity from the mixed sequences. However, running the second sequence at a lower clock speed can be interesting too. If sequence B only steps every time sequence  A finishes, for example, the resulting effect is transposition of the sequence A by the current value of sequence B. So, if sequence B is just 2 steps (N=2), steps every time sequence A ends, and consists of the voltages {0, .585}, what would happen is that sequence A switches between being played unmodified and then transposed up by .585V. The point of adding .585 volts specifically is because this corresponds to a perfect fifth. The way you can arrive at this is via the relation between musical intervals and voltages in the 1V/Oct system. Checking the reference list [here](https://en.wikipedia.org/wiki/List_of_intervals_in_5-limit_just_intonation), we see that a perfect fifth corresponds to a 3/2 ratio. With 0V as the baseline, we obtain the corresponding voltage required to attain a perfect fifth interval using the formula (log(3) - log(2))/log(2) (see [here](https://modwiggler.com/forum/viewtopic.php?t=178596) for details). 