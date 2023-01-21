# Retime up video to fit a set duration using FFMPEG

The code first gets the duration of the video, then it calculates the number of seconds to slow down the video and finally it uses ffmpeg command to slow down the video by the calculated number of seconds and saves it to an output file.

This code is written in bash, a Unix shell, and it's using the ffprobe command to get the duration of a video file named "input.mp4" and ffmpeg command to slow down the video by 8 seconds.

The first line is using the ffprobe command to get the duration of the video, which is passed as an argument to the command. The command's output is the video's duration, which is stored in the "duration" variable.

The second line is using the echo command to print the value of the "duration" variable, which is then passed to the bc command. The bc command is a simple calculator language that is often used in shell scripts. The purpose of this line is to change the representation of the duration from a string to a number, which will be used in the next line.

The third line is using the ffmpeg command to slow down the video by 8 seconds. The command takes the input video file "input.mp4" and applies the filter "setpts=(8/$st)*PTS" to adjust the video's playback speed. This filter is using the value stored in the "st" variable which is the duration of the video in seconds. The argument 8 is the number of seconds by which the video should be slowed down. The -t 8 option specifies that the output video should be 8 seconds long. The output video file is named "output-retimed.mp4".
