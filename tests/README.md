Battery Test
=======================

Tests based around BB10 WebWorks blackberry.system.batterystatus 


Tests to perform:

1. Confirm correct battery state is being returned
    
    a) If plugged into power source ==> .isPlugged === 1
    
    b) If not plugged into power source ==> .isPlugged === 0
    
2. Confirm correct battery level is being returned

    a) If plugged into power source ==> next battery level > previous battery level
    
    b) If not plugged into power source ==> next battery level < previous battery level
    
    
    
Structure of test:
______________

battery.htm : screen for battery test

battery.js : jasmine tests along with helper functions



How battery.htm is designed:
------------------------------

    a) User will be told to ensure device is not plugged into any source power and click OK to continue
    
    b) EventListener for batterystatus change will be created
    
    c) User will be told to plug device into a power source
    
    d) test: that .isPlugged === 1  & obtain .level
    
    e) User will be told to wait for battery level to change
    
    f) confirm .isPlugged === 1, test: .level > previous .level
    
    g) User will be told to disconnect power source
    
    h) test: .isPlugged === 0 & obtain .level
    
    i) User will be told to wait for battery level to change
    
    j) confirm .isPlugged === 0, test: .level < previous .level
    
    DONE
