 - **Website**: http://cfengine.com/

 - **Hello world**:
   ```
   body common control {
        bundlesequence => { "hi" };
}

body server control {
        allowusers => { "andres" };
        cfruncommand => "/var/cfengine/bin/cf-agent";
}

# how to admit only exec?
bundle server access_rules {
        access:
                any::
                        "/var/cfengine/bin/cf-agent"
                                admit => { ".*" };
}

bundle agent hi {
        reports:
                powerpc::
                        "This is a PowerPC Host";
                any::
                        "Hello!";
}
```
