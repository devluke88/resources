# Basics

###

### Upload to S3 via Postman



<pre><code>// S3 Endpoint
<strong>// https://&#x3C;my_bucket>.s3.amazonaws.com/&#x3C;file_destination>
</strong>// Example: 
//https://test-bucket.s3.amazonaws.com/37fc355a-85e5-42d8-b359-03acf238ad0b/raw_files/37fc355a-85e5-42d8-b359-03acf238ad0b

// Generate SHA256 sum:
shasum -a 256 my_file.txt | cut -f1 -d\ | xxd -r -p | base64

// Postman Steps:
1. Set up AWS SIgnature Auth type in Postman
2. Use additional keys in Heders:
    * x-amz-checksum-sha256: your base64 encoded checksum sha256, for instance: 9WjDllRkasTzHyHRbXREEETNNgP0BP/I/16zlE91EH4=
    * x-amz-server-side-encryption: AES256
3. Use binary in Body and select file from hard drive
4. Send request
</code></pre>

### Unlock the state in Terraform

```
terraform force-unlock LOCK_ID
```

### Unlock the state in Terraspace

```
bundle exec terraspace force-unlock <stackName> <Id>    
```

```
# unintall gem
gem uninstall terraspace -v 1.0.2
```

##
