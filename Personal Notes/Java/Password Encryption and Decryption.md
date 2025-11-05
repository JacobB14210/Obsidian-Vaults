# Cipher
```java
package util;

import javax.crypto.Cipher;
import javax.crypto.spec.SecretKeySpec;
import java.nio.charset.StandardCharsets;
import java.util.Base64;

public class PasswordUtil {
	private static final String ALGORITHM = "AES";
	private static final String keyString = "13514210AJNAGCEO"; // 16 characters
	// Object used to initialize a Cipher with an AES algorithm and the keyString
	private static final SecretKeySpec KEY = new SecretKeySpec(keyString.getBytes(StandardCharsets.UTF_8), "AES");
	
	public static String encrypt(String password) throws Exception {
		// Initialize AES Cipher into encrypt mode
		Cipher cipher = Cipher.getInstance(ALGORITHM);
		cipher.init(Cipher.ENCRYPT_MODE, KEY);
		// Converts the encrypted password to bytes, and Encrypts it with AES key
		byte[] encryptedPassword = cipher.doFinal(password.getBytes(StandardCharsets.UTF_8));
		// Encodes the result as a String
		return Base64.getEncoder().encodeToString(encryptedPassword);
	}
	
	public static String decrypt(String encryptedPassword) throws Exception {
		// Initializes AES Cipher into decrypt mode
		Cipher cipher = Cipher.getInstance(ALGORITHM);
		cipher.init(Cipher.DECRYPT_MODE, KEY);
		// Decodes the String into bytes
		byte[] decodedPassword = Base64.getDecoder().decode(encryptedPassword);
		// Decryptes the bytes using AES and the same key
		byte[] originalPassword = cipher.doFinal(decodedPassword);
		// Returns original password
		return new String(originalPassword, StandardCharsets.UTF_8);
	}
}

```