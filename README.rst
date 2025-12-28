Sample and Hold
===============

A sample and hold circuit does what it says: samples the input voltage at the start of an interval and holds that voltage at the output for the duration of the interval. 

References
----------

#. Yves Usson, "Random module: Noise generator and Sample & Hold", `Yusynth <http://yusynth.net/Modular/EN/NOISE/index.html>`_
#. Moritz Klein, "Designing a sample & hold circuit from scratch", `Youtube <https://www.youtube.com/watch?v=kIJqzkRe4do>`_
#. Rene Schmitz, "YASH (Yet another Sample and Hold)", `schmitzbits.de <https://schmitzbits.de/sah.html>`_
#. Eddy Bergman, "Revised sample and hold", `eddybergman.com <https://www.eddybergman.com/2023/03/revisedsampleandhold.html>`_

Overview
--------

There are two basic topologies for S&H circuits: JFET + capacitor and the LF398. 

Feature Ideas
-------------

* Internal clock and external trigger (rising edge)

  * swing on the internal clock? two bit counter + JFET in parallel with extra series R

* Glide output

  * exponential (RC low pass)
  * linear? constant slope would be I into C with a comparator to start/stop; constant time would need a second S&H to compute B-A to scale I into C (I = C dV/dt: fix dt, dV=B-A, Iref = (B-A)/Rref + current mirror into C)

* Don't do
  
  * Offset / output level (): use mixer/attenuver
  * VC-clk: use an external clock on the trigger



