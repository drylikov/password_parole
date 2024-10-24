An OTP client-server application for local password managing based on **gen_server**.

Usage
-----

Run following command:

```
~ rebar3 build && rebar3 shell
```

and then you can use it, like this:

```erlang
Erlang/OTP 18 [erts-7.3] [source] [64-bit] [smp:4:4] [async-threads:10] [kernel-poll:false]

Eshell V7.3  (abort with ^G)

2> parole:start().
{ok,<0.40.0>}

3> Resource = <<"www.github.com">>.
<<"www.github.com">>

4> Password = <<"MyNotEncryptedPassword">>.
<<"MyNotEncryptedPassword">>

5> parole:add(Resource, Password).
ok

6> parole:lookup(Resource).
true

7> parole:get(Resource, decrypted).
<<"MyNotEncryptedPassword">>
```