A loopless and branchless $O(1)$ algorithm to generate the next Dyck word.
=====

Let integer be any C/C++ unsigned integer type up to 64-bits long.
Given a Dyck word the following code returns the next Dyck word of the same size, provided it exists.
<code>
integer next_dyck_word(integer w) {
  integer a = w & -w;
  integer b = w + a;
  integer c = w ^ b;
  c = (c / a >> 2) + 1;
  c = c * c - 1;
  c = (c & 12297829382473034410u) | b;
  return c;
}
</code>

Copyright (C) 2014 Cassio Neri Moreira

<a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/"><img alt="Creative Commons License" style="border-width:0" src="http://i.creativecommons.org/l/by-sa/4.0/88x31.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/">Creative Commons Attribution-ShareAlike 4.0 International License</a>.