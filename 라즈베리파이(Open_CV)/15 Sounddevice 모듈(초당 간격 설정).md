# 15 Sounddevice 모듈(초당 간격 설정)

-  5초마다 녹음

```python
import sounddevice as sd  # 5초마다 녹음스
duration = 5.5 # seconds
def callback(indata, outdata, frames, time, status):
if status:
print(status)
outdata[:] = indata
with sd.Stream(channels=1, callback=callback):
sd.sleep(int(duration * 1000))
```

- 저장하기

```python
# 저장하기

import sounddevice as sd 
import soundfile as sf
fs = 44100 # Sample rate
seconds = 3 # Duration of recording
myrecording = sd.rec(int(seconds * fs), samplerate=fs, channels=1)
sd.wait() # Wait until recording is finished
sf.write('output.wav', myrecording, fs) # Save as WAV file 
```

- 임의의 길이 녹음하기

```python
# 임의의 길이 녹음하기
import io
import queue
import sounddevice as sd
import soundfile as sf

samplerate = 44100

sd.default.samplerate = samplerate
sd.default.device = 1
# sd.default.device = '마이크(USB PnP Sound Device), MME'
sd.default.channels = 1

q = queue.Queue()
recMem = io.BytesIO()
def callback(indata, frames, time, status):
    if status:
        print(status, file=sys.stderr)
    q.put(indata.copy()) # 녹음 데이터 큐에 추가



try:
    with sf.SoundFile(recMem, mode='x', format='wav', 
            samplerate=samplerate, channels=channels) as file:
    with sd.InputStream(callback=callback):
        print('#' * 80)
        print('press Ctrl+C to stop the recording')
        print('#' * 80)
        while True:
            # 큐에 녹음 데이터가 있다면 추출하여 파일에 기록
            file.write(q.get())

except KeyboardInterrupt:
    print(recMem.tell())
    # 완료 처리
    print('\nRecording finished: ') 
except Exception as e:
    print(e)
```

