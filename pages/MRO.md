- > *take the head of the first list, i.e L[B1][0]; if this head is not in
  the tail of any of the other lists, then add it to the linearization
  of C and remove it from the lists in the merge, otherwise look at the
  head of the next list and take it, if it is a good head.  Then repeat
  the operation until all the class are removed or it is impossible to
  find good heads.  In this case, it is impossible to construct the
  merge, Python 2.3 will refuse to create the class C and will raise an
  exception.*
	- `L[C(B1 ... BN)] = C + merge(L[B1] ... L[BN], B1 ... BN)`
		- **where** `B1 ... BN` are the **parents** of `C` and `merge` is implemented as described above, and `L` is the `linearization`
- # By The Way
- you can not have such inheritance structure
	- ```
	  A
	  B
	  C(A,B)
	  D(B,A)
	  E(C,D) #Error
	  ```
- # Example
- ![](https://miro.medium.com/v2/resize:fit:875/1*MabrPMoWx8dk-C8g_utkzA.png)
	- lets solve the `mro` for this hierarchy
	- ```
	  MRO(F) = F + merge(CO + AO + BO + CAB) = FCABO
	  MRO(G) = G + merge(AO + DO + AD) = GADO
	  MRO(H) = H + merge(BO + DO + EO + BDE) = HBDEO
	  MRO(I) = I + merge(FCABO + GADO + HBDEO + FGH) = IFCGAHBDEO
	  
	  # [I, F, C, G, A, H, B, D, E, object]
	  ```