# WEB APPLICATION PENETRATION TESTING.

- ffuf (Fuzz Faster U Fool)
	-- # ffuf -u https://example.com/FUZZ -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -mc 200,204,301,302,403 -t 100 -r
		-mc (match only responses with status code.)
		-u (target url where FUZZ keyword will be replaced with by each word)
		-w (path to wordlist)
		-t (increase thread default is 40)
		-r (follow redirects)

	-- # ffuf -u https://example.com/DIR -w /usr/share/wordlists/dirb/common.txt -mc 200 -p DIR
		-p (use this keyword to replace p for placeholder)


	-- # ffuf -u https://example.com/login.php?user=USER&pass=PASS -w users.txt:USER -w passwords.txt:PASS
		if wants to use multiple placeholders they can be used like this.
		to detect a valid username and password. we can use filters in this command.
		| Flag  | Purpose                                                                |
		| ----- | ---------------------------------------------------------------------- |
		| `-fc` | **Filter by status code** (e.g., ignore 401 Unauthorized)              |
		| `-fs` | **Filter by response size** (e.g., ignore if response is same length)  |
		| `-fw` | **Filter by number of words**                                          |
		| `-fl` | **Filter by number of lines**                                          |
		| `-mr` | **Match regex or string in body** (e.g., "Welcome", "Dashboard", etc.) |

	
