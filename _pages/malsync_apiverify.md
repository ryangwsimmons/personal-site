---
title: MAL Verification - Success
layout: single
permalink: /sync-to-mal-for-anilist/mal-verify/
---

Your MyAnimeList account has been successfully verified with the application. Please enter the code below into the app to continue:

<code id="mal_auth_code">
</code>

<script type="application/javascript">
document.onreadystatechange = function() {
    if (document.readyState === 'complete') {
        // Get the auth code from the URL query params
        const params = new URLSearchParams(window.location.search);
        const auth_code = params.get('code');

        // Set the text content of the code area to the code
        const auth_code_area = document.getElementById('mal_auth_code');
        auth_code_area.textContent = auth_code;
    }
}
</script>