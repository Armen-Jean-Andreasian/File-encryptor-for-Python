# File encryptor for Python 

---
## Intro

This script encrypts your files using **Fernet** with a custom `master.key`, deletes them, and generates new encrypted files, which your are free to share.
- It's especially useful for encrypting sensitive data, such as secrets, that you need to gitignore or add to a remote host.
- This allows you to securely share files while maintaining the confidentiality of sensitive information.

### Addition:
In my similar project [File Encryptor for Ruby](https://github.com/Armen-Jean-Andreasian/File-Encryptor-for-Ruby) **AES-256-CBC** was used, here we use **Fernet**. 

Well, yeah `AES-256-CBC` is more advanced in terms of raw encryption power, however `Fernet` is also good enough for this task.

---
## Important Security Note

**If you lose your `key` file or the `salt` file which will be generated, you will lose access to your encrypted files.** This script is framework-independent and isolated.


---
## Usage Example

```python
from encoder import FileEncoder, FilesToEncodeType

if __name__ == "__main__":
	MASTER_KEY_PATH = "master.key"  # enter the relative path to your key
	FILES_TO_ENCODE: FilesToEncodeType = './file_to_encode1', './file_to_encode2'  # enter the relative paths of your actual files
	
	file_encoder = FileEncoder(
		master_key_path=MASTER_KEY_PATH,
		files_to_encode=FILES_TO_ENCODE
	)
	
	file_encoder.encode()
	file_encoder.decode()
```

