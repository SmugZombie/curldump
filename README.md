## What curldu.mp ?
curldu.mp is a free and open-source service to exchange small files with cURL.

## Usage :
* To upload a file :
  `curl -T /home/myfile curldu.mp`
or
  `curl -File=@/home/myfile curldu.mp`

* To upload multiple files :
  `curl -T {/home/myfile, file2} curldu.mp`
or
  `curl -File=@/home/myfile -File1=@myfile curldu.mp`

* To upload a stream :
  `curl http://curldu.mp | curl -T - curldu.mp`

curldu.mp returns a (list of) URLs. To get a shorter URL, send the 'X-SHORT: yes' HTTP header :
  `curl -H "X-SHORT: yes" -T /home/myfile curldu.mp`

## Dependencies
curldu.mp depends on :
* Flask
* uwsgi
* python-magic
* sqlite3

## Limitations
curldu.mp needs a webserver (Nginx/Apache) to handle Chunked Transfer Encoding (used when content is piped)

## Credits :
curldu.mp is an alternative to http://chunk.io under the free software ISC licence. Fork me at https://github.com/ledeuns/curldump.




