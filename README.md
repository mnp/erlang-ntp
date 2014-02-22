# Erlang retreive and decode from an NTP server.

Eshell V5.7.2  (abort with ^G)
1> c(ntp).
{ok,ntp}
2> ntp:ask().
{{li,0},
 {vn,3},
 {mode,4},
 {stratum,3},
 {poll,0},
 {precision,-20},
 {rootDelay,440},
 {rootDispersion,2662},
 {referenceId,130,126,24,24},
 {referenceTimestamp,1309987720.951235},
 {originateTimestamp,-2208988800},
 {receiveTimestamp,1309988125.884236},
 {transmitTimestamp,1309988125.2857387},
 {clientReceiveTimestamp,1309988664.216},
 {offset,-538.9302613735199}}


Please note, this function doesn't implement the full NTP
algorithm. It just does the first step: poll a server without taking
into account round trip time, jitter, dispersion and all those good
NTP clustering things.  In other words, it answers the question "what
time did that server think it was, a few dozen ms ago?"  It doesn't
answer the question, "what time is it now?"

Licensed under the [Apache License, Version 2.0](http://www.apache.org/licenses/LICENSE-2.0).
