## Uwanted Parasitic BJTs



 Modifications were made to the **SCN6M_SUBM.10.tech** File.
 Modified Technology File:  **SCN6M_SUBM_modified.10.tech**
 
 Note: 
 **To ensure that the Vertical Parasitic PNP BJT was recognized and extracted correctly, the line below was added to the Technology File.**

```
 device bjt PNP nwell,nsc/a,nsd pdiff,pdc/a pwell,space/w,psc/a,psd 
```

However, this line seems to cause unwanted BJTs to appear in places where they are not their, even when only a partial requirement is met for the BJT.
