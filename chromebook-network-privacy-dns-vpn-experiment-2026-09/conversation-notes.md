# Conversation Notes

## Starting point

The user described concern that network systems may observe or react to information a person accesses, including ordinary browsing. The conversation then focused on practical privacy controls rather than trying to establish a motive.

## Sequence preserved

1. A search was made for a free VPN suitable for Chromebook use.
2. Proton VPN was identified as an option with unlimited data and strong privacy features.
3. The Proton app was discussed in relation to ChromeOS/Android-container behavior.
4. The experiment moved toward encrypted DNS as a lighter alternative.
5. Quad9 (9.9.9.9) was considered for DNS-over-HTTPS.
6. The user reported a network failure after turning off Proton VPN and testing custom DNS.
7. The conversation attributed the failure to aggressive Comcast/Xfinity router behavior; this was an interpretation, not an established diagnosis.
8. Cloudflare (1.1.1.1) was proposed as another encrypted-DNS option.
9. ECH and a Chrome flag were proposed as a possible additional privacy mechanism.
10. The later conversation corrected the stronger "stealth" characterization: ECH is not a complete invisibility mechanism.
11. The user reported that the Cloudflare diagnostic page itself could not be reached from the current system/network configuration.

## Known versus inferred

Known from the user's report:
- configuration changes were attempted;
- connectivity subsequently failed;
- the Cloudflare diagnostic page could not be reached.

Not established:
- who or what caused the failure;
- whether the router inspected browsing content;
- whether Comcast deliberately blocked the settings;
- whether any geographic endpoint indicates surveillance.

## Constructive direction

Use reversible tests and exact error messages. The experiment should produce a small factual record rather than a theory of hidden intent.
