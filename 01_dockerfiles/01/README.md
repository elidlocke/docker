###To build the image:
docker build -t ex01 .
###To run the server:
docker run -ti --rm -p 9987:9987/udp -e TS3SERVER_LICENSE=accept ex01
###To Connect:
1) Download the Mac Version of Teamspeak https://www.teamspeak.com/en/downloads
2) Start a new teamspeak
3) Copy paste the host ip of Char (or whatever docker machine we are using)
4) Copy paste the token given in the terminal to init the chat session
