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

##Common Issues:

# <hash_map> is deprecated and will be REMOVED. Please use <unordered_map>.

Open `StlUtls.h` (Code\CryEngine\CryCommon\), and add another at line 21 with `#define _SILENCE_STDEXT_HASH_DEPRECATION_WARNINGS`.

#identifier "IParticleEmitter" is undefined

Comment-out lines 414 to 430 in `CryArray.h` (Code\CryEngine\CryCommon\).

#'mem_fun' : is not a member of 'std'

Include `<functional>` (`#include <functional>`) in `GrabHandler.h` (`Code\GrabHandler.h`).
