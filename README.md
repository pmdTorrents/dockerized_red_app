docker pull will9512/dockerized_red_app

docker run -e DISPLAY=$DISPLAY -v /tmp/.X11-unix:/tmp/.X11-unix:rw \
-v /path/to/dockerize_red_tool-config.ini:/app/dockerize_red_tool-config.ini \
-v /path/to/script_output_dirs/audio_directory:/app/audio_directory \
-v /path/to/script_output_dirs/video_directory:/app/video_directory \
-v /path/to/script_output_dirs/script_data_directory:/app/script_data_directory \
will9512/dockerized_red_app

