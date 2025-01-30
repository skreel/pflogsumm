In postfix if you create transport maps and assign different syslog names, so that the log reflects which transport map was used, pflogsumm requires that you use the --syslog_name paramater to include these logs in the report. Problem is there is only one syslog_name parameter. 

This code adds a --syslog_name2 parameter to pflogsumm so that one can have report include up to two transports w/ different syslog names. Technically three total, as "postfix" is included always.

This code also modifies the report output to show count of emails delivered via those transport queues. Sample output:

Grand Totals
------------
messages

    874   received
    884   delivered
    860    via <syslog_name>
      0    via <syslog_name2>
      0   forwarded
      6   deferred  (28  deferrals)
      0   bounced
      0   rejected (0%)
      0   reject warnings
      0   held
      0   discarded (0%)

 506556   bytes received
    526k  bytes delivered
      6   senders
      2   sending hosts/domains
      6   recipients
      2   recipient hosts/domains
