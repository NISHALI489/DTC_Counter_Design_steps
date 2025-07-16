
# DTC_Counter_Design_steps
DTC Diagnostic Trouble Code

**Operation cycle:**
1. Ignitation ON-OFF
2. Power ON-OFF

**3. Status Bits:**
   1. Test Fail bit
   2. Pending bit
   3. Confirmed bit

**Counters**
1. Debounce Counter
2. Occurenece Counter
3. Failure Counter
4. Healing Counter
5. Aging Counter
6. Failure Detection Counter

**Modules Name:**
1.PTU: Power transfer Unit
2.RDM: Rear Drive Module 
3.RDMS: Rear Drive Module Shifter(Second varient of RDM)

7. **Battery working voltage range**
   Requirements:
   a. Let's assume here as per client requirement our battery is working under voltage from 5v to 15 volt.
   b. If Battery voltage is go less than 5v it shall be considered as STG(Short to Ground) fault.
   c. If Battery voltage is go more than 15v it shall be considered as STB(Short to Battery) fault.
   d. If Battery voltage is less than 500mv it shall be considered as OPEN fault.
   e. Sensor erratic behaviour.

14. **Counters:**
15. **a. Debounce counter:**
16. It will check for the fault if it is available for same or single opration cycle, then status or fault bit set to test failed bit.

17. **b. Occurenece counter:**
18. It will check for the fault if it is available for same as well as next operation cycle, then status or fault bit set to test failed  to Pending bit.

19. **c. Failure Counter:**
    It will check for the fault if it is available for same as well as next operation cycle, then status or fault bit set to pending to confirmed bit.
    However bit is confirmed state fault will be logged into NvM memory.
    And Warning Indicator will be activated.

23. **d. Healing counter:**
24. Once the Warning Indicator is turned ON the Healing counter will be comes into the picture.
25. Healing Counter will check for the fault if it is not Available for same or single operation cycle then only Warning Indicator will be turned off.

26. **NOTE: We have limited size of Memory so here at certain condition we need to remove DTC from Memory or NvM.**

27. **e. Aging Counter:**
28. It will check for the fault in same opration cycle as well as next opration cycle, if fault is not available then and then only it will remove fault from the NvM memory.
    

    

