# Crysis-Wars-Source-Code
Original, unedited source-code for budding modders out there.

Originally created in order to aid those [attempting to fix the 'SwapEndian' error with C++11 and later versions](http://stackoverflow.com/questions/24580523/swapendian-doesnt-work-in-c11-what-changed) (link points to a question on Stack Overflow by me), but also because I keep losing the original source-code :-).

Feel free to fork and create your own game mod :-).

# Useful Stuff

------

# Uncap Server Slot Limit

From the [CryEngine Forums](http://www.cryengine.com/community/viewtopic.php?t=66401):

    static void SvMaxPlayers(ICVar* cvar)
    {
       int value = cvar->GetIVal();
       if (value < 2) 
       {
          value=2;
          cvar->Set(value);
          return;
          }
      }
  
  pConsole->GetCVar("sv_maxplayers")->SetOnChangeCallback(SvMaxPlayers);
  
Goes in GameCVars.cpp.
