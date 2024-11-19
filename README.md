# Spack

This tool is a Bash wrapper that simplifies the manipulation of compressed files of various formats in a unified way. The supported formats are:

- `rar`
- `zip`
- `tar`
- `gz`
- `xz`
- `tar.gz`
- `tar.xz`
- `gpg`
- `gz.gpg`
- `xz.gpg`
- `tar.gz.gpg`
- and others.

In general, the supported tools are:

- `rar`
- `zip`
- `tar`
- `gz`
- `xz`
- `gpg`

### Current Supported Operations

- Compression
- Decompression

### Possible Roadmap for Future Features

- Listing files
- Appending files
- Removing files

This tool is primarily designed for interactive usage. If you need to create a script, it is recommended to use the actual tools directly. This is because I cannot guarantee compatibility across versions during the early development phase. However, compatibility may be ensured in the future.

---

## Usage Examples

### Compress all files in the current working directory to the output file `compressed.tar.gz`:

```bash
spack -c * -o compressed.tar.gz
```

The tool will automatically detect the compression format based on the file extension. For example:

```bash
spack -c * -o compressed.tar     # Creates an uncompressed tarball
spack -c * -o compressed.gz      # Compresses to gzip (only if one file is passed, otherwise, an error occurs)
spack -c * -o compressed.zip     # Creates a zip file
```

If the extension is not explicit, or if you want to force a specific format, use the `--format` option:

```bash
spack -c * -o compressed.zip --format tar.gz # Compress using tar and gzip
```

The values for the `--format` option correspond to common file extensions for each compression format.

### Assign a Password to the Compressed File

Use the `--pass` option and provide a password:

```bash
spack -c * -o compressed.tgz.gpg --pass 123456
```

If no password is specified after `--pass`, the tool will prompt you to enter one interactively, hiding your input for security. If the selected format does not support encryption, an error will be raised.

For formats like `gpg`, the `--pass` option is mandatory. If no password is provided, an error will occur.

To see additional options, run:

```bash
spack -h
```

### Decompression

The process is similar to compression but expects a single input file. The `-o` option specifies the output directory. For example:

```bash
spack -d compressed.tar.gz -o output/dir
```

This command overwrites any existing files by default. Use the `-i` option to make decompression interactive, prompting you before overwriting files.

---

## Development Philosophy

This tool will remain a single Bash file to ensure easy installation and minimalism. I prioritize clean, small, and efficient code over speed or unnecessary complexity. If a feature is too complex, I may decide not to implement it.

---

## Credits and Support

This is a hobby, educational, and practical project mainly created for personal use. I'm currently focused on learning programming and creating content to prepare for a future career.  

If you’d like to support this project, a star on GitHub would mean a lot!  

You can also follow me on social media (mainly **spanish**):  
- **GitHub**: You’re already here!  
- **YouTube**: [@jvivas-code](https://www.youtube.com/@jvivas-code)  
- **LinkedIn**: [Jimy Aguasviva](https://www.linkedin.com/in/jimy-aguasviva-781b32200/)  
- **X (Twitter)**: [@soworksl](https://x.com/soworksl)  
