![exampleimage](https://i.imgur.com/5hJiNmt.png)
![exampleimage](https://i.imgur.com/gKRiEGA.png)

##Install:

# do the stuff to make the stream allow for the webgl things to happen...
sudo cp mjpeg_streamer.hpp /home/pi/cpp-mjpeg-streamer/include/nadjieb/<br>
sudo cp publisher.hpp /home/pi/cpp-mjpeg-streamer/include/nadjieb/net/<br>
sudo rm -rf /usr/local/include/nadjieb<br>
sudo cp -r /home/pi/cpp-mjpeg-streamer/include/nadjieb /usr/local/include/nadjieb<br>

# add proper handling so that the template does false color
sudo cp eventemitter2.js /home/pi/cinemate/src/module/app/static/js/<br>
sudo cp mjpegcanvas.js /home/pi/cinemate/src/module/app/static/js/<br>
sudo cp template.html /home/pi/cinemate/src/module/app/templates/<br>

# recompile and reinstall cinepi
cd ~/cinepi-raw/<br>
sudo rm -rf build<br>
sudo meson setup build<br>
sudo meson compile -C build<br>
sudo install --group=root --owner=root ~/cinepi-raw/build/cinepi/cinepi-raw "/usr/local/bin/cinepi-raw"<br>
