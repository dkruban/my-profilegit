flowchart TD
    %% Style Definitions
    classDef container fill:#050508,stroke:#00f3ff,stroke-width:2px,color:#fff,rx:10,ry:10,filter:drop-shadow(0px 0px 10px #00f3ff);
    classDef title fill:none,stroke:none,color:#fff,font-size:20px,font-weight:bold;
    classDef subtitle fill:none,stroke:none,color:#00f3ff,font-size:14px;
    classDef statBox fill:#1a1a2e,stroke:#ff00ff,stroke-width:1px,color:#fff,rx:5;
    classDef statBar fill:#ff00ff,stroke:none;
    classDef badge fill:#bc13fe,stroke:#fff,stroke-width:1px,color:#fff,rx:15,font-size:12px;
    classDef launch fill:none,stroke:#0aff0a,stroke-width:2px,color:#0aff0a,rx:20,stroke-dasharray: 5 5,font-weight:bold;

    %% Main Card Node
    Card[<table border='0'>
        <tr><td colspan='2'><b>RUBAN.M</b><br/><span style='color:#00f3ff'>▸ AI PROMPTER ◂</span></td></tr>
        <tr><td colspan='2' style='padding: 10px; border-radius: 50%; border: 2px dashed #00f3ff; display:inline-block; text-align:center; width:80px; height:80px;'>R.M</td></tr>
        
        <tr><td align='left'><b>Prompt Eng</b></td><td align='right'>92%</td></tr>
        <tr><td colspan='2'><hr style='background:#00f3ff; height:4px; border:none; width:92%'/></td></tr>
        
        <tr><td align='left'><b>AI/ML</b></td><td align='right'>87%</td></tr>
        <tr><td colspan='2'><hr style='background:#ff00ff; height:4px; border:none; width:87%'/></td></tr>
        
        <tr><td align='left'><b>Creative</b></td><td align='right'>79%</td></tr>
        <tr><td colspan='2'><hr style='background:#bd00ff; height:4px; border:none; width:79%'/></td></tr>
        
        <tr><td align='left'><b>Auto</b></td><td align='right'>95%</td></tr>
        <tr><td colspan='2'><hr style='background:#0aff0a; height:4px; border:none; width:95%'/></td></tr>

        <tr><td colspan='2' style='padding-top:15px'>
            <span style='background:rgba(0,243,255,0.1); border:1px solid #00f3ff; padding:2px 8px; border-radius:10px; margin:2px; font-size:10px'>Claude</span>
            <span style='background:rgba(255,0,255,0.1); border:1px solid #ff00ff; padding:2px 8px; border-radius:10px; margin:2px; font-size:10px'>GPT-4</span>
            <span style='background:rgba(255,0,255,0.1); border:1px solid #ff00ff; padding:2px 8px; border-radius:10px; margin:2px; font-size:10px'>Gemini</span>
        </td></tr>
        
        <tr><td colspan='2' style='padding-top:10px; border: 1px solid #0aff0a; border-radius: 15px; color:#0aff0a; font-weight:bold'>LAUNCH ↗</td></tr>
    </table>]:::container

    %% Animated Connecting Lines (The "Pulse" Effect)
    %% Note: Mermaid animations are simple. We simulate complexity with styles.
    
    linkStyle 0 stroke:#00f3ff,stroke-width:4px,opacity:0.5
