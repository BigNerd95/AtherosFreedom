# Dynamic Country Code

Allows the atheros driver to set the regulatory domain for the phy devices too.  

Without this patch:  
```
root@TL841v8:~# iw reg set AU
root@TL841v8:~# iw reg get
global
country AU: DFS-ETSI
	(2400 - 2483 @ 40), (N/A, 36), (N/A)
	(5150 - 5250 @ 80), (N/A, 23), (N/A), NO-OUTDOOR, AUTO-BW
	(5250 - 5350 @ 80), (N/A, 20), (0 ms), NO-OUTDOOR, DFS, AUTO-BW
	(5470 - 5600 @ 80), (N/A, 27), (0 ms), DFS
	(5650 - 5730 @ 80), (N/A, 27), (0 ms), DFS
	(5730 - 5850 @ 80), (N/A, 36), (N/A)
	(57000 - 66000 @ 2160), (N/A, 43), (N/A), NO-OUTDOOR

phy#0
country US: DFS-FCC
	(2402 - 2472 @ 40), (N/A, 30), (N/A)
	(5170 - 5250 @ 80), (N/A, 23), (N/A), AUTO-BW
	(5250 - 5330 @ 80), (N/A, 23), (0 ms), DFS, AUTO-BW
	(5490 - 5730 @ 160), (N/A, 23), (0 ms), DFS
	(5735 - 5835 @ 80), (N/A, 30), (N/A)
	(57240 - 63720 @ 2160), (N/A, 40), (N/A)

```

With this patch:  
```
root@TL841v8:~# iw reg set AU
root@TL841v8:~# iw reg get
global
country AU: DFS-ETSI
	(2400 - 2483 @ 40), (N/A, 36), (N/A)
	(5150 - 5250 @ 80), (N/A, 23), (N/A), NO-OUTDOOR, AUTO-BW
	(5250 - 5350 @ 80), (N/A, 20), (0 ms), NO-OUTDOOR, DFS, AUTO-BW
	(5470 - 5600 @ 80), (N/A, 27), (0 ms), DFS
	(5650 - 5730 @ 80), (N/A, 27), (0 ms), DFS
	(5730 - 5850 @ 80), (N/A, 36), (N/A)
	(57000 - 66000 @ 2160), (N/A, 43), (N/A), NO-OUTDOOR

phy#0
country AU: DFS-ETSI
	(2400 - 2483 @ 40), (N/A, 36), (N/A)
	(5150 - 5250 @ 80), (N/A, 23), (N/A), NO-OUTDOOR, AUTO-BW
	(5250 - 5350 @ 80), (N/A, 20), (0 ms), NO-OUTDOOR, DFS, AUTO-BW
	(5470 - 5600 @ 80), (N/A, 27), (0 ms), DFS
	(5650 - 5730 @ 80), (N/A, 27), (0 ms), DFS
	(5730 - 5850 @ 80), (N/A, 36), (N/A)
	(57000 - 66000 @ 2160), (N/A, 43), (N/A), NO-OUTDOOR
 
```
