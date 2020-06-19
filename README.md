# mk_oracle.cfg

## using REMOTE_INSTANCE_*

* instantclient basic + sqlplus is needed
* tnsping is needed too, which is not provided at least for recent versions
  I created /usr/lib/oracle/19.6/client64/bin/tnsping, that just calls exit 0
  (if tnsping fails, mk_oracle falls back to host:port/sid, which does not make sense for me..)


## using cloudwallet

    cd /etc/check_mk
    unzip /path/to/cloudwallet/wallet_DB205632611318.zip
    # edit path in sqlnet.ora
    perl -pi.bak -e 's-DIRECTORY=".*"-DIRECTORY="/etc/check_mk"-g' sqlnet.ora 
