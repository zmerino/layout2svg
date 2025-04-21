<h1 align=center> Fork of layout2svg by Z.D.M. on 4/20/25 </h1>

An update was made to `cli.py` to handle path finding for the inkscape bin directory for Linux. 
A function `parse_lyp_to_yaml()` was added to parse the open source GSD editor KLayout's layer files (.lyp) 
and format them into the expected .yaml format.

**Notes to get running:**

Run the following:

```bash
conda create -n gds2svg python=3.10
conda activate gds2svg
conda install -c conda-forge numpy lxml gdstk klayout
```

Update the requirements file with `klayout==0.28.17.post1` and run:

```bash
pip install --no-deps -r requirements.txt
```

Install an editable version of the package locally using `pip install -e .` inside the cloned directory.

Use command `layout2svg -i Double_Dot_test.gds -o Double_dot_test.svg -t Double_dot_test.lyp` with the in-house test 
files to ensure everything was installed/setup properly.

<h1 align=center> layout2svg </h1>

<div align=justify>
<p> This is a simple tool to convert an integrated circuit layout saved in OASIS / GDSII file format to a .SVG image file. The tool supports direct export of the SVG file into the Inkscape desktop app. This tool was written with the goal of rendering any layout in a desktop or web application. </p>
</div>

<h2 align=center> Installation </h2>

<h3 align=center> MacOS, Linux, Windows </h3>

```bash
pip install layout2svg
```

<h2 align=center> Usage - Command Line Interface </h2>

```bash
layout2svg -i <input_file_path [.gds/.oas]> -o <output_file_path [.svg]> -t <layerstack_file_path [.ymls]>
```

<h2 align=center> Examples </h2>

<p>
Running the example with the mock layerstack file and layout provided in the <a href="tests/data/">examples</a>, by running the following command:
</p>

```bash
layout2svg -i ./tests/data/crossed_metal.gds -t ./tests/data/mock_layers.ymls -o ./tests/data/crossed_metal.svg
```

<p>
can generate the following SVG image:
</p>

<p align=center>


<img src="tests/data/crossed_metal.png" width=400/>

</p>
