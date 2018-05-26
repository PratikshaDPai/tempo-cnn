.. image:: https://img.shields.io/badge/License-AGPL%20v3-blue.svg
    :target: https://www.gnu.org/licenses/agpl-3.0

=========
Tempo-CNN
=========

Tempo-CNN is a simple CNN-based framework for estimating temporal properties
of music tracks.

First and foremost, Tempo-CNN is a tempo estimator. To determine the global tempo of
an audio file, simply run the script

.. code-block:: console

    tempo -i my_audio.wav

You may specify other models and output formats (`mirex <http://www.music-ir.org/mirex/wiki/2018:Audio_Tempo_Estimation>`_,
`JAMS <https://github.com/marl/jams>`_) via command line parameters.

E.g. to create JAMS as output format and the model originally used in the ISMIR 2018
paper [1], please run

.. code-block:: console

    tempo -m ismir2018 --jams -i my_audio.wav

Instead of estimating a global tempo, Tempo-CNN can also estimate local tempi in the
form of a tempogram. This can be useful for identifying tempo drift.
To create such a tempogram, run

.. code-block:: console

    tempogram -p my_audio.wav

As output, ``tempogram`` will create a ``.png`` file. Additional options to select different models
and output formats are available.

Tempo-CNN provides experimental support for temporal property estimation of Greek
folk music [2]. The corresponding models are named ``fma2018`` (for tempo) and ``fma2018-meter``
(for meter). To estimate the meter's numerator, run

.. code-block:: console

    meter -m fma2018-meter -i my_audio.wav


Installation
============

Clone this repo and run ``setup.py install`` using Python 3.6:

.. code-block:: console

    git clone https://github.com/hendriks73/tempo-cnn.git
    cd tempo-cnn
    python setup.py install


License
=======

Source code and models can be licensed under the GNU AFFERO GENERAL PUBLIC LICENSE v3.
For details, please see the `LICENSE <LICENSE>`_ file.


Citation
========

If you use Tempo-CNN in your work, please consider citing it:

.. code-block:: latex

   @inproceedings{madmom,
      Title = {{A single-step approach to musical meter estimation using a convolutional neural network}},
      Author = {Schreiber, Hendrik and M{\"u}ller Meinard},
      Booktitle = {Proceedings of the 19th International Society for Music Information Retrieval Conference ({ISMIR})},
      Month = {9},
      Year = {2018},
      Address = {Paris, France}
   }


References
==========

.. [1] Hendrik Schreiber, Meinard Müller, `A single-step approach to musical meter estimation using
    a convolutional neural network <http://www.tagtraum.com/download/2018_schreiber_tempo_cnn.pdf>`_
    Proceedings of the 19th International Society for Music Information
    Retrieval Conference (ISMIR), Paris, France, Sept. 2018.
.. [2] Hendrik Schreiber, *Technical Report: Tempo and Meter Estimation for
    Greek Folk Music Using Convolutional Neural Networks and Transfer Learning*
    Proceedings of the 8th International Workshop on Folk Music Analysis (FMA),
    Thessaloniki, Greece, June 2018.