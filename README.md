# Play-MP3
Play MP3
- From local:
MediaPlayer song = MediaPlayer.create(MainActivity.this, R.raw.nuocmat); 
song.start();

Stop: 
onPause(); 
song.pause();

- From Internet:
  public void PlayNhacMp3(String url){
        //url = "http://khoapham.vn/download/vietnamoi.mp3";
        MediaPlayer mediaPlayer = new MediaPlayer();
        mediaPlayer.setAudioStreamType(AudioManager.STREAM_MUSIC);
        try {
            mediaPlayer.setDataSource(url);
            mediaPlayer.prepareAsync();
            mediaPlayer.setOnPreparedListener(new MediaPlayer.OnPreparedListener() {
                @Override
                public void onPrepared(MediaPlayer mp) {
                    mp.start();
                }
            });

        } catch (IOException e) {
            e.printStackTrace();
        }

    }
