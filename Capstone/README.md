Scope:
* start with 1 instrument -> multiple instrument

Process flow from other research:
1. Music21 http://web.mit.edu/music21/ -> extract musical notation of MIDI files
2. Keras -> create and train LSTM model / BLSTM
3. Sample model architecture: LSTM, # of nodes (512), dropout layer (30%?), dense layers, activation layer (Softmax), loss function (categorical cross-entropy), optimizer (RMSprop), Gated Recurrent Unit(?)

Preliminary questions:
* How to evaluate if the model is improving over time? -> generate music score for comparison at some epochs for checkpoints?
* From the generated midi outputs, how to play the notes? -> play_midi method from play.py file / use an external MIDI player / convert MIDI file to the mp3 (https://www.lifewire.com/midi-file-2621979)

Techniques employed by other research:
* limiting to songs from the same key(?) http://nickkellyresearch.com/python-script-transpose-midi-files-c-minor/
* Variable length notes and rests: introduce long notes, short notes and rests -> pitch and duration of a note as separate values
* Song structure: verse1-chorus-verse2-chorus-bridge-chorus
* Multi instrument attempts: MelodyCNN (to drive melody generation from 1 instru) -> conditional harmony CNN (to generate for other instru with dependency). Another one is VAE (Variational auto-encoders)

Improvements from other research:
* Learn patterns in songs rather than manually piecing together parts
* Take note duration as a separate input to the network rather than treating each pitch/duration separately
* Expand to multiple instruments
* Move away from midi files and produce/learn from actual MP3s
* Learn the time step, sequence length, and time signature
* Introduce randomness to emulate “human error/experimentation”
* Allow for multiple keys
* Learn how to use intros and outros
* Handle unknown notes

Sources:
Source - Zenodo: https://zenodo.org/record/3464194#.YVaH7UZBzDI
Source - Midiworld: https://www.midiworld.com/search/?q=jazz
Source - saxshed: https://saxshed.com/midi-files/
Source - Lakh Pianoroll dataset https://salu133445.github.io/lakh-pianoroll-dataset/
Source - Lakh Midi dataset https://salu133445.github.io/lakh-pianoroll-dataset/
Source - million song dataset http://millionsongdataset.com/
Free music archive: https://github.com/mdeff/fma
Accessing Spotify API via Spotipy: https://spotipy.readthedocs.io/en/latest/
Tech: keras, RNN, music21 http://web.mit.edu/music21/doc/moduleReference/moduleConverter.html

Reference:
https://www.hackerearth.com/blog/developers/jazz-music-using-deep-learning/
    Github from previous line: https://github.com/shubham3121/music-generation-using-rnn
https://towardsdatascience.com/how-to-generate-music-using-a-lstm-neural-network-in-keras-68786834d4c5
    Github from previous line: Classical piano composer https://github.com/Skuldur/Classical-Piano-Composer
Making music with ML https://towardsdatascience.com/making-music-with-machine-learning-908ff1b57636
    Github from previous line: https://github.com/tylerdoll/music-generator
YT Creating jazz music with ML (LSTM) https://youtu.be/LGma1oarvtk
    Github from previous line: https://github.com/Mittaladitech/Jazz-Solo-with-an-LSTM-Network
Lo-fi Hip Hop music generator https://ai.plainenglish.io/building-a-lo-fi-hip-hop-generator-e24a005d0144
Multi-instrument RNN https://towardsdatascience.com/generating-music-using-deep-learning-cb5843a9d55e
Andrew Shaw pop music generator https://towardsdatascience.com/creating-a-pop-music-generator-with-the-transformer-5867511b382a
Open AI Musenet: https://openai.com/blog/musenet/
Open AI Jukebox: https://openai.com/blog/jukebox/

GAN-based
Cornell Yang MidiNet https://arxiv.org/abs/1703.10847
Cornell MuseGAN https://arxiv.org/abs/1709.06298 -> multi instruments multitracks -> result: https://salu133445.github.io/musegan/
