# hacfb
!/bin/sh

#perulangan
ulang='y'
while [ $ulang = 'y' ];
do
  #menu utama
  echo '1) install nico.py'
  echo '2) install brute.py'
  echo '3) install darkfb'
  exho '0) exit '
  #masukan atau input
  read -p 'Masukkan Pilhan anda : ' pil; 
  #kondi jika input = 1 maka akan menginstall brute.py
  if [ $pil = '1' ]
  then
      echo 'installing brute.py'
      cd $HOME
      apt update && apt upgrade -y
      apt intall php -y
      apt install git
      git clone https://github.com/nicoleus/brute.py
      echo 'installing succes....! '
      sleep 1
  #kondisi jika input = 2 maka akan menginstall nico.py
  elif [ $pil = '2' ];
  then
      echo 'installing nico.py '
      cd $HOME
      apt update  && apt upgrade -y
      apt install python -y
      apt install git -y
      git clone https://github.com/nicoleus/nico.py
      cd nico.py
      pip install -r requirements.txt
      python2 nicoleus.py
      echo 'installing succes...! '
      sleep 1
  #kondisi jika input = 3 maka akan menginstall darkfb
  elif [ $pil = '3' ];
  then
      echo 'installing darkfb'
      cd $HOME
      apt update && apt upgrade -y
      apt install git
      git clone https://github.com/nicoleus/darkfb
      cd darkfb
      sh install.sh
      echo 'installing succes.. '
      sleep 1
  #kondisi jika input = 0 maka akan keluar dari tools
  elif [ $pil = '0' ];
  then
      echo 'bye bye cuk.....! '
      sleep 2
      exit
  #kodisi else
  else
      echo 'ERROR : Wrong Input....! '
      sleep 1
      echo $ulang
  fi
done
