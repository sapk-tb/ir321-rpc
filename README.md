gcc dict.c -o dict
./dict

rpcgen rdict.x 
rpcgen -Sm rdict.x > Makefile
rpcgen -Sc rdict.x > rdict_clnt_main.c 
rpcgen -Ss rdict.x > rdict_svc_prog.c 

make

./rdict_client localhost
./rdict_server
