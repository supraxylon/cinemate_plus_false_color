# do the stuff to make the stream allow for the webgl things to happen...
sudo cp mjpeg_streamer.hpp /home/pi/cpp-mjpeg-streamer/include/nadjieb/net/
sudo cp publisher.hpp /home/pi/cpp-mjpeg-streamer/include/nadjieb/
sudo install --group=root --owner=root /home/pi/cpp-mjpeg-streamer/include/nadjieb /usr/local/include/nadjieb

# add proper handling so that the template does false color
sudo cp eventemitter2.js /home/pi/cinemate/src/module/app/static/js/
sudo cp mjpegcanvas.js /home/pi/cinemate/src/module/app/static/js/
sudo cp template.html /home/pi/cinemate/src/module/app/templates/

# recompile and reinstall cinepi
cd ~/cinepi-raw/
rm -rf build
meson setup build
meson compile -C build
sudo install --group=root --owner=root ~/cinepi-raw/build/cinepi/cinepi-raw "/usr/local/bin/cinepi-raw"