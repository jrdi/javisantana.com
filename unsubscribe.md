---
layout: base_data
---
<div class="container">
  <div class="entry">
    <h1><a href="/">≗</a> Unsubscribe</h1>
    
    <div id="unsubscribe-form" class="entry space" style="text-align: center; margin-top: 2em;">
      <h2>Unsubscribe from updates</h2>
      <form onsubmit="handleUnsubscribe(event)" style="margin: 2em 0; display: flex; flex-direction: column; align-items: center; gap: 1em;">
        <input 
          type="email" 
          id="email" 
          placeholder="Enter your email"
          style="padding: 8px 12px; font-size: 16px; width: 300px;"
          required
        >
        <textarea
          id="reason"
          placeholder="Why are you unsubscribing? (optional)" 
          style="padding: 8px 12px; font-size: 13px; width: 300px; height: 60px; resize: vertical;"
        ></textarea>
        <button 
          type="submit"
          style="padding: 8px 16px; font-size: 16px; background: #ff9f71; border: none; color: #1a1a1a; cursor: pointer; width: 300px;"
        >
          Unsubscribe
        </button>
      </form>
      <div id="unsubscribe-message" style="display: none; margin-top: 1em;"></div>
    </div>
  </div>

  <script>
    async function handleUnsubscribe(e) {
      e.preventDefault();
      
      const emailInput = document.getElementById('email');
      const reasonInput = document.getElementById('reason');
      const messageDiv = document.getElementById('unsubscribe-message');
      const email = emailInput.value.trim();
      const reason = reasonInput.value.trim();

      // Basic email validation
      const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
      if (!emailRegex.test(email)) {
        messageDiv.style.display = 'block';
        messageDiv.style.color = '#ff4444';
        messageDiv.textContent = 'Please enter a valid email address';
        return;
      }

      try {
        const response = await fetch('https://api.tinybird.co/v0/events?name=subscriptions', {
          method: 'POST',
          headers: {
            'Authorization': 'Bearer p.eyJ1IjogIjM5ZjBiNjdiLThjODQtNDU2Zi1iZTdmLWQ4MDhmMzhjN2YxMCIsICJpZCI6ICJiOTZlZDAyMi0wYmY2LTRhNTktYjZkYi05YzJhOWMyZGJiYTUiLCAiaG9zdCI6ICJldV9zaGFyZWQifQ.zmMJvSsUPvSZ5LBezK7cTc2A6TXBsg701nyXVprtWBk',
            'Content-Type': 'application/json'
          },
          body: JSON.stringify({
            email: email,
            reason: reason,
            timestamp: new Date().toISOString(),
            unsubscribe: 1,
            source: window.location.href
          })
        });

        if (response.ok) {
          messageDiv.style.display = 'block';
          messageDiv.style.color = '#4CAF50';
          messageDiv.textContent = "You have been unsubscribed, it's sad yo see you leave.";
          emailInput.value = '';
          reasonInput.value = '';
        } else {
          throw new Error('Unsubscription failed, contact me so I sort this out.');
        }
      } catch (error) {
        messageDiv.style.display = 'block';
        messageDiv.style.color = '#ff4444';
        messageDiv.textContent = 'Something went wrong. Please try again later.';
      }
    }
  </script>

  <div class="entry more close"><a href="/">≗</a></div>
</div>