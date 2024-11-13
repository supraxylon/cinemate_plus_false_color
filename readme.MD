# do the stuff to make the stream allow for the webgl things to happen...
sudo cp mjpeg_streamer.hpp /home/pi/cpp-mjpeg-streamer/include/nadjieb/net/<br>
sudo cp publisher.hpp /home/pi/cpp-mjpeg-streamer/include/nadjieb/<br>
sudo install --group=root --owner=root /home/pi/cpp-mjpeg-streamer/include/nadjieb /usr/local/include/nadjieb<br>

# add proper handling so that the template does false color
sudo cp eventemitter2.js /home/pi/cinemate/src/module/app/static/js/<br>
sudo cp mjpegcanvas.js /home/pi/cinemate/src/module/app/static/js/<br>
sudo cp template.html /home/pi/cinemate/src/module/app/templates/<br>

# recompile and reinstall cinepi
cd ~/cinepi-raw/<br>
rm -rf build<br>
meson setup build<br>
meson compile -C build<br>
sudo install --group=root --owner=root ~/cinepi-raw/build/cinepi/cinepi-raw "/usr/local/bin/cinepi-raw"<br>
