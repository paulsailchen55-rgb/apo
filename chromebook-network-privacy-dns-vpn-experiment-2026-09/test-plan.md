# Reversible Test Plan

## Goal

Determine whether encrypted DNS can operate reliably in the current Chromebook/network configuration without disrupting ordinary connectivity.

## Baseline

Record:
- Chrome version;
- ChromeOS version;
- whether ordinary HTTPS sites load;
- exact error messages;
- current Secure DNS setting;
- whether a VPN is active.

## Test A — ordinary connectivity

Use several ordinary HTTPS destinations. Record load/failure and exact errors.

## Test B — encrypted DNS

Enable Chrome's built-in Secure DNS option for one provider, if available. Test ordinary sites and the provider's diagnostic page.

Do not simultaneously change VPN settings, browser flags, router settings, and DNS.

## Test C — recovery

If connectivity fails, return to the last known-good setting and confirm ordinary connectivity before attempting another variable.

## Test D — ECH

Only after baseline DNS behavior is understood should ECH support be investigated. Record whether the relevant browser/version supports it and what the feature is documented to protect.

## Interpretation rule

A failed test establishes that a configuration did not work under the tested conditions. It does not establish why it failed.

## Desired output

A small table of configuration, result, exact error, what changed, and what remains uncertain.
