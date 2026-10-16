## A Digital Elevation Model Service

Use rasterio package to extract elevation data from .hgt files.

- rasterio, https://rasterio.readthedocs.io/en/stable/topics/reading.html
- Flask, https://flask.palletsprojects.com/en/stable/
- Flask + socketio, https://flask-socketio.readthedocs.io/en/latest/intro.html
- srtm + .hgt files, https://viewfinderpanoramas.org/dem1d.html
- https://viewfinderpanoramas.org/Coverage%20map%20viewfinderpanoramas_org1.htm


HGT File Format  
An HGT file covers an area of 1°x1°. Its south western corner can be deduced from its file name: for example, n51e002.hgt covers the area between N 51° E 2° and N 52° E 3°, and s14w077.hgt covers S 14° W 77° to S 13° W 76°. The fils size depends on the resolution. If this is 1", there are 3601 rows of 3601 cells each; if it is 3", there are 1201 rows of 1201 cells each. The rows are laid out like text on a page, starting with the northernmost row, with each row reading from west to east. Each cell has two bytes, and the elevation at that cell is 256*(1st byte) + (2nd byte). It follows that a 3" HGT file has a file length of 2 x 1201 x 1201. SRTM 3" cells are calculated by calculating the mean of 1" cells and their eight neighbors. It follows that the highest local point is likely to higher than the highest SRTM 3" cell. The difference should vary with the steepness of the local relief.
