🎶 Sine Wave Generator in C

This project generates a sine wave audio tone using C and writes it to a raw PCM file (sine.raw). The generated file can be played back with audio tools like Audacity, VLC, or command-line players.

📌 How it Works

Sampling rate: 44,100 Hz (CD quality).

Duration: 2 seconds.

Frequency: 440 Hz (A4 note, standard tuning pitch).

Amplitude: 16-bit signed integer range (max value = 32767).

Each audio sample is calculated as:

𝑠
𝑎
𝑚
𝑝
𝑙
𝑒
=
32767
×
sin
⁡
(
2
𝜋
𝑓
𝑡
)
sample=32767×sin(2πft)

where:

𝑓
f = tone frequency

𝑡
t = time for each sample
▶️ How to Run

Compile:

gcc sine.c -o sine -lm


Run:

./sine


Output file:

sine.raw will be created in the same directory.

🎧 How to Play the File

With Audacity:

Open sine.raw

Import as Raw Data

Settings:

Encoding: Signed 16-bit PCM

Byte order: Little Endian

Channels: 1 (Mono)

Sample rate: 44100 Hz

With ffplay (from FFmpeg):

ffplay -f s16le -ar 44100 -ac 1 sine.raw


With VLC:

Just open sine.raw directly.

📂 Output Example

Plays a 2-second pure tone at 440 Hz (A4 note).

Sounds like a tuning fork 🎵
