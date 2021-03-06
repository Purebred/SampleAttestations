This repository features a set of key attestations and corresponding X.509 certificate files generated by various Pixel, Surface Pro and Yubikey devices. The attestations were generated in support of issuance of device and user certificates. In each case, the following artifacts are present (except in the case of a Pixel 1, in which case only the first artifacts below are present):

- a device attestation and corresponding certificate is supplied as extracted from a JSON exchange with a portal. 
- a device SCEP request and corresponding certificate
- a set of user SCEP requests and corresponding certificates

For Pixel and Yubikey devices, the attestation format is a certs-only SignedData structure. For Surface Pro, the attestation format is a CMC request. For each SCEP request, a custom object identifier was used to label an attribute containing the attestation format.

Trust anchors for each are present in the trust anchors folder.

Yubikey attestation information is available [here](https://developers.yubico.com/PIV/Introduction/PIV_attestation.html). Example source code is available [here](https://github.com/Yubico/yubico-piv-tool). Trust anchor was obtained from [here](https://developers.yubico.com/PIV/Introduction/piv-attestation-ca.pem).

Android attestation information is available [here](https://source.android.com/security/keystore/attestation) and [here](https://developer.android.com/training/articles/security-key-attestation). Trust anchors were obtained from sample code [here](https://github.com/googlesamples/android-key-attestation/tree/master/server/src/main/java/com/android/example).

Surface Pro attestation information is available in various locations: [ASN.1](https://msdn.microsoft.com/en-us/library/mt242068.aspx), [attestation statement](https://msdn.microsoft.com/en-us/library/dn408990.aspx) and [TPMS_ATTEST](https://trustedcomputinggroup.org/wp-content/uploads/TPM-Rev-2.0-Part-2-Structures-00.99.pdf). The CMC spec is [here](https://tools.ietf.org/html/rfc5272). The trust anchors were obtained from the CAB file located  [here](https://docs.microsoft.com/en-us/windows-server/virtualization/guarded-fabric-shielded-vm/guarded-fabric-install-trusted-tpm-root-certificates).