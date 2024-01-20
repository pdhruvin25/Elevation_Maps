# Elevation Maps Program

This C program processes elevation maps represented as 2D arrays. The main functionalities include reading and writing PGM images, extracting connected regions with the same elevation, and a helper function to check surrounding pixels.

## Functions

### 1. writePGMimage Function

Writes a PGM image file based on the provided image array. The output file is named "output.pgm." It assumes the array has size (size_x x size_y) and contains unsigned char values.

### 2. readPGMimage Function

Reads a PGM image file into the specified image array. It assumes the image is of size (size_x x size_y) and handles the PGM file format, skipping comments and verifying file size.

### 3. check_around Function

A recursive function that explores the connected region around a given pixel in the elevation map. It marks explored pixels with value 2 in the `value_arr` array and sets the corresponding value in the `levelset_map` array.

### 4. extract_levelset Function

The main function for extracting connected regions with the same elevation. It calls the `check_around` function to identify and mark connected pixels in the `levelset_map`.

### 5. main Function

- Reads an elevation map from the file "Mars_elevation_crop1.pgm" into the `image_array`.
- Initializes a `levelset_map` and clears it to all zeros.
- Calls the `extract_levelset` function with initial coordinates (5, 5).
- Writes the resulting `levelset_map` to "output.pgm" using `writePGMimage`.

## Example Usage

The program reads an elevation map, extracts a connected region with the same elevation as the specified initial coordinates, and writes the result to an output PGM file.

## Important Notes

- The elevation maps are assumed to have values ranging from 1 to 255, with pixels of the same value indicating the same elevation.
- The program uses a recursive approach to traverse connected pixels, marking them in `value_arr` and updating `levelset_map` accordingly.
