### Objective
This project tries to create new jazz music using RNN deep learning model (Recurrent Neural Network).

### Data

5 jazz song covers by Doug McKenzie downloaded from [his website](https://bushgrafts.com/midi/) are selected as the training inputs. These are predominantly piano covers, some of which have light accompaniments of other instruments such as bass guitar.

They are ingested in MIDI format (Musical Instrument Digital Interface), which is a format used to store instructions to play music, such as the note (a single sound), the pitch (the frequency of the sound), and more.

Processing and working with MIDI format is done using a Python library called [Music21 from MIT](http://web.mit.edu/music21/).

Before we continue further, I would like to credit the works by [Shubham Gupta](https://www.hackerearth.com/blog/developers/jazz-music-using-deep-learning/) and [Sigurður Skúli](https://towardsdatascience.com/how-to-generate-music-using-a-lstm-neural-network-in-keras-68786834d4c5), which I've used as references.

### Training and Modelling

Training is done using a RNN model called LSTM (Long Short Term Memory) across 400 epochs. The model architecture used can be referred to in the file 'model.ipynb'

### Result

To assess the performance and output across training, weights of the training model at 5 different epochs (epoch 1, 100, 204, 303 and 382) are used to predict and generate notes.

These outputs (both midi and mp3 files) are available to access in the model folder.

From listening to the MIDI files, we can observe massive improvements across epochs:
- In epoch 1, 1 note is played over and over for the entirety of the song
- In epoch 100, the model has now learned to play more than 1 note although there are still instances of repetitive notes and absence of any chords
- In epoch 382, the model has learned to play chords and have little to no repetitive notes. However, all notes have the same duration and there are no pauses between notes

### Next Steps
1. Ingest rest notes (offsets) as inputs in order for the model to learn pauses in songs
2. Try to create structure of actual songs, e.g. verse-chorus-verse-chorus-bridge
3. Add an additional instrument, e.g. bass
