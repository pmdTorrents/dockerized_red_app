


fill in config

docker pull will9512/dockerized_red_app

run:
    xhost +

run:
    docker run -e DISPLAY=$DISPLAY -v /tmp/.X11-unix:/tmp/.X11-unix:rw \
    -v /path/to/dockerize_red_tool-config.ini:/app/dockerize_red_tool-config.ini \
    -v /path/to/script_output_dirs/audio_directory:/app/audio_directory \
    -v /path/to/script_output_dirs/video_directory:/app/video_directory \
    -v /path/to/script_output_dirs/script_data_directory:/app/script_data_directory \
    will9512/dockerized_red_app

paste in links to scrape, if you put in an artists year it will iterate to 2024 ex.:

    https://play.nugs.net/browse/artist/128/year/2005
    
    will get all shows for band 128 from 2005-2024


close gui and rerun the above command to refresh the list (fixing)


select one (or multiple) shows from the left then:
    - download audio - get tracks in format defined in config
*************************************************************************************************
*this worked before but is untested in docker so far

    - get and upload 
       -if flac only radial button is selected
         - searches red for the band, if the flac is missing (ONLY CHECKS THE CONCERT RECORDINGS CATAGORY) it will download the flac and upload to red with formatted descriptns and cover images. 
      - if transcode to mp3 is selected, searches red for the band:
        - if the flac is missing (ONLY CHECKS THE CONCERT RECORDINGS CATAGORY) it will download the flac, transcode to v0 and or 320 depending on whats missinf and upload to red with formatted descriptns and cover images.
        - if flac exists but v0 and/or 320 is missing it will downlaod flac from nugs and transcode/upload
*************************************************************************************************
      - if you fill in tracker info and use deluge or rtorrent it will download the new torrent red makes and add to your client seeding
    
when finished run:
    xhost -
