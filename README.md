# PotatoRepo
buds1, buds1sr = librosa.load('buds1.m4a')
ipd.Audio(x, rate=sr)

buds2, buds2sr = librosa.load('buds2.m4a')
ipd.Audio(x, rate=sr)

oth1, oth1sr = librosa.load('toOther1.m4a')
ipd.Audio(x, rate=sr)

oth2, oth2sr = librosa.load('toOthers2.m4a')
ipd.Audio(x, rate=sr)

# FFT using scipy
Buds1 = scipy.fft.fft(buds1)
Buds1_mag = np.absolute(Buds1)
buds1f = np.linspace(0, sr, len(Buds1_mag)) # frequency variable

Buds2 = scipy.fft.fft(buds2)
Buds2_mag = np.absolute(Buds2)
buds2f = np.linspace(0, sr, len(Buds2_mag))

Oth1 = scipy.fft.fft(oth1)
Oth1_mag = np.absolute(Oth1)
oth1f = np.linspace(0, sr, len(Oth1_mag))

Oth2 = scipy.fft.fft(oth2)
Oth2_mag = np.absolute(Oth2)
oth2f = np.linspace(0, sr, len(Oth2_mag))

# Plot the spectrum:

plt.figure(figsize=(13, 5))
plt.plot(buds1f, Buds1_mag) # magnitude spectrum
plt.xlabel('Frequency (Hz)')

plt.figure(figsize=(13, 5))
plt.plot(buds2f, Buds2_mag) # magnitude spectrum
plt.xlabel('Frequency (Hz)')

plt.figure(figsize=(13, 5))
plt.plot(oth1f, Oth1_mag) # magnitude spectrum
plt.xlabel('Frequency (Hz)')

plt.figure(figsize=(13, 5))
plt.plot(oth2f, Oth2_mag) # magnitude spectrum
plt.xlabel('Frequency (Hz)')
