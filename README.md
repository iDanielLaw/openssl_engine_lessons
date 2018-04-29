# openssl_engine_lessons
OpenSSL Engineのサンプルコード

# v1

参照: https://www.openssl.org/blog/blog/2015/10/08/engine-building-lesson-1-a-minimum-useless-engine/

```
cd v1
make
make test
```

以下の出力があればOK
```
openssl engine -t -c `pwd`/./bin/silly-engine.so
(/***/***/src/openssl_engine_lessons/v1/./bin/silly-engine.so) A silly engine for demonstration purposes
Loaded: (silly) A silly engine for demonstration purposes
     [ available ]

```

# v2

参照: https://www.openssl.org/blog/blog/2015/11/23/engine-building-lesson-2-an-example-md5-engine/

```
cd v2
make
make test
```

以下の出力があればOK
```
openssl engine -t -c `pwd`/./bin/md5-engine.so
(/***/***/src/openssl_engine_lessons/v2/./bin/md5-engine.so) A simple md5 engine for demonstration purposes
Loaded: (MD5) A simple md5 engine for demonstration purposes
 [MD5]
     [ available ]
echo whatever | openssl dgst -engine `pwd`/./bin/md5-engine.so -md5
engine "MD5" set.
(stdin)= d8d77109f4a24efc3bd53d7cabb7ee35
echo whatever | openssl dgst -md5
(stdin)= d8d77109f4a24efc3bd53d7cabb7ee35
```
