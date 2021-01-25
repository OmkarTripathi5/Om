from pygame import mixer
import time
mixer.init()
def song_player(file,stopper):
    mixer.music.load(file)
    while True:
        mixer.music.play()
        stop = input()
        if (stopper == stop):
            mixer.music.stop()
        break

def log_file(msg):
    with open ("execise.txt","a") as f:
        f.write(f"{time.ctime(time.time())} = {msg}\n")

water_time = time.time()
eyes_time = time.time()
phy_time = time.time()
if __name__ == '__main__':
    while True:
        final_time = time.time()
        if final_time - water_time > 1800 or final_time - water_time == 1800:
            print("Drink Water and if you want to stop the rimender then type \' drank \'")
            song_player("WaterSound.mp3","drank")
            log_file("you drink water")
            water_time = time.time()

        if final_time - eyes_time > 1200 or final_time - eyes_time == 1200:
            print("Do eyes execise and if you want to stop the rimender then type \' done \'")
            song_player("eyes.mp3","done")
            log_file("you done your eyes execise")
            eyes_time = time.time()

        if final_time - phy_time > 2400 or final_time - phy_time == 2400:
            print("Do any physical execise and if you want to stop the rimender then type \' donephy \'")
            song_player("phy.mp3","drank")
            log_file("You done your physical execise")
            phy_time = time.time()



