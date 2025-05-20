# fluent-bit-test
test case for fluent-bit hanging 

the repo contains the `docker-compose.yaml` file along with the needed config and test log files to reproduce the fluent-bit hanging issue.

## Steps:

clone the repo:
```bash 
git clone https://github.com/AzureLeMoon/fluent-bit-test.git
```

then inside the repo ,run fluent-bit: 
```bash
docker compose up
```

now to test the tail input 
```bash
 echo '{"time":"2024-11-08T18:56:32.721610509Z","level":"INFO","prefix":"-","file":"test.go","line":"396","message":"test"}' >> test.log
```

now to reproduce the hanging issue:
```bash
cat test-long.log >> test.log
```

after this the in_tail plugin stops working.
