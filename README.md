# FileCrypt
File Encryption using a passphrase
<p>
 FileCrypt program uses AES-GCM-SIV for encryption. The program uses the AES-GCM-SIV package written by Adam Langley (the same copyright <a href="https://github.com/agl/gcmsiv/commit/e8dcd2f151dc75b6fd5697d94c2bb57eccd05e21"> required </a> who is also the co-author of the <a href="https://datatracker.ietf.org/doc/rfc8452/?">RFC </a>. For more information and details of AES-GCM-SIV, you can refer to <a href="https://cyber.biu.ac.il/aes-gcm-siv/"> AES-GCM-SIV Mode of Operation </a> and Cloudflare has a <a href="https://blog.cloudflare.com/tls-nonce-nse/"> great blog </a> on the different cipher suite for TLS use-case. 
<p>
Filecrypt program encrypt or decrypt one file at a time. The necessary parameters needed are explained within the help for FileCrypt. These are <br>
<p>

`Usage: filecrypt [options...] <path/filename> ` <br>
Options: <br>
  -e  Encryption set to true by default, to decrypt set -e=false or -e=0 <br>
  -p  passphrase to be used for encryption or decryption. Please remember the passphrase. <br>
  -f  filename of file after encryption or decryption. You can include the path for the file to be created. <br>
<p>
 Please note that FileCrypt does not stored the passphrase given by the user, the same passphrase used for encryption needs to be used to decrypt on the same file. And in all files store in media/disk, it can be proned to corruption by various reasons (corruption, disk failures etc), it is highly recommended that user backup their original file. Any corruption on the encrypted file may cause issues with decryption.
<p>  
FileCrypt has been tested to work on text/ASCII, pdf, video movie (MOV) and should work on most file format. The User is requested to test it out. Currently, no support is being offered and the user acknowledge they are fully responsible on the usage of FileCrypt on the health status of their own files. <p>
<br>
The latest binary for FileCrypt can be downloaded <a href="https://github.com/maxng07/FileCrypter/releases"> here </a>
<h2>Caveats </h2>
An encryption test (on old i7 CORE MAC) done on a 2GB movie file saw 4.27GB of memory consume, 2GB read and 2GB write. 6 threads and a single process are started, as the program currently does not use parallelism and concurrency. The current program reads the file into memory before performing encryption/decryption and writing to disk. As such the current FileCrypt may not work for large files where memory limitation is a concern. A significant huge file for encryption or decryption would also takes significant time to complete. <br>
At the same time, on the same machine spec, a slightly over 20MB ASCII log file took slightly over 8s to encrypt and similar to decrypt. <br>
Feedback welcome from users of FileCrypt.
<p>

 
 <h2>Licensing </h2>
 Filecrypt uses a GO package for AES-GCMSIV which has a copyright license as part of BoringSSL. The copyright notice as is below
<p>

/* Copyright (c) 2017, Google Inc.
 *
 * This code was written to support development of BoringSSL and thus is
 * considered part of BoringSSL and under the same license.
 *
 * Permission to use, copy, modify, and/or distribute this software for any
 * purpose with or without fee is hereby granted, provided that the above
 * copyright notice and this permission notice appear in all copies.
 *
 * THE SOFTWARE IS PROVIDED "AS IS" AND THE AUTHOR DISCLAIMS ALL WARRANTIES
 * WITH REGARD TO THIS SOFTWARE INCLUDING ALL IMPLIED WARRANTIES OF
 * MERCHANTABILITY AND FITNESS. IN NO EVENT SHALL THE AUTHOR BE LIABLE FOR ANY
 * SPECIAL, DIRECT, INDIRECT, OR CONSEQUENTIAL DAMAGES OR ANY DAMAGES
 * WHATSOEVER RESULTING FROM LOSS OF USE, DATA OR PROFITS, WHETHER IN AN ACTION
 * OF CONTRACT, NEGLIGENCE OR OTHER TORTIOUS ACTION, ARISING OUT OF OR IN
 * CONNECTION WITH THE USE OR PERFORMANCE OF THIS SOFTWARE. */ 
