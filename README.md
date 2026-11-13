# tsukiyo-2-0. 
<!doctype html>
<html lang="es">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width,initial-scale=1,viewport-fit=cover">
  <meta name="theme-color" content="#111321">
  <title>Tsukiyo 2.0</title>
  <style>
    :root{color-scheme:dark;--bg:#0c0e18;--panel:#151827;--panel2:#1b2032;--line:#2b3046;--text:#f4f2ff;--muted:#a7abc2;--accent:#b9a2ff;--accent2:#8c78d8;--good:#8ed8b2;--bad:#ff9eaa;--gold:#e8d4a3}
    *{box-sizing:border-box}
    body{margin:0;background:radial-gradient(ellipse at 80% -10%,#292343 0,transparent 38%),var(--bg);color:var(--text);font:15px/1.5 system-ui,-apple-system,Segoe UI,Roboto,sans-serif;min-height:100vh}
    button,input,select,textarea{font:inherit}
    .wrap{max-width:1000px;margin:auto;padding:22px 16px 48px}
    header{display:flex;align-items:center;gap:14px;margin:8px 0 24px}
    .moon{width:48px;height:48px;border-radius:17px;background:linear-gradient(145deg,#c8b6ff,#7964c3);display:grid;place-items:center;color:#171323;font-size:27px;box-shadow:0 8px 30px #8c78d844}
    h1{font-size:24px;line-height:1.1;margin:0;letter-spacing:.2px}
    .sub{color:var(--muted);font-size:13px;margin-top:5px}
    .tag{margin-left:auto;border:1px solid var(--line);border-radius:999px;padding:6px 10px;color:var(--gold);font-size:11px;letter-spacing:.08em}
    .hero,.panel,.auth{background:linear-gradient(145deg,#191d2d,#131625);border:1px solid var(--line);border-radius:20px;padding:20px;box-shadow:0 16px 45px #0003}
    .hero{margin-bottom:16px}
    .eyebrow{font-size:11px;color:var(--accent);letter-spacing:.15em;text-transform:uppercase}
    .hero h2{font-size:22px;margin:6px 0 4px}
    .hero p{color:var(--muted);margin:0;max-width:680px}
    .grid{display:grid;grid-template-columns:1fr 1fr;gap:16px}
    .panel{margin-bottom:16px}
    .panel h3{font-size:16px;margin:0 0 14px}
    .muted{color:var(--muted)}
    label{display:block;color:var(--muted);font-size:12px;margin:12px 0 6px}
    input,select,textarea{width:100%;border:1px solid var(--line);border-radius:11px;background:#0f1220;color:var(--text);padding:12px;outline:none}
    input:focus,select:focus,textarea:focus{border-color:var(--accent2);box-shadow:0 0 0 3px #8c78d822}
    textarea{min-height:100px;resize:vertical}
    button{border:0;border-radius:11px;padding:11px 15px;background:var(--accent);color:#171323;font-weight:700;cursor:pointer}
    button.secondary{background:#292e43;color:var(--text);border:1px solid var(--line)}
    button.ghost{background:transparent;color:var(--muted);border:1px solid var(--line)}
    button:disabled{opacity:.55;cursor:wait}
    .actions{display:flex;gap:9px;flex-wrap:wrap;margin-top:14px}
    .status{padding:10px 12px;border-radius:10px;background:#20243a;color:var(--muted);font-size:13px;margin-top:14px;white-space:pre-wrap}
    .status.good{color:var(--good);background:#163026}.status.bad{color:var(--bad);background:#351d29}
    .auth{max-width:480px;margin:30px auto}
    .auth h2{margin:0 0 5px}
    .auth p{margin:0;color:var(--muted);font-size:13px}
    .toolbar{display:flex;gap:10px;align-items:center;flex-wrap:wrap;margin-bottom:14px}
    .toolbar input{flex:1;min-width:160px}
    .memory{border:1px solid var(--line);background:#111524;border-radius:13px;padding:14px;margin-top:10px}
    .memory-top{display:flex;gap:8px;align-items:center;flex-wrap:wrap}
    .memory strong{font-size:14px}
    .pill{font-size:10px;color:var(--accent);border:1px solid #514674;border-radius:999px;padding:3px 8px}
    .memory p{margin:8px 0;color:#d4d4e2;white-space:pre-wrap;overflow-wrap:anywhere}
    .meta{font-size:11px;color:var(--muted)}
    .empty{padding:22px;text-align:center;color:var(--muted);border:1px dashed var(--line);border-radius:13px}
    .hidden{display:none!important}
    footer{text-align:center;color:#747991;font-size:11px;margin-top:26px}
    @media(max-width:700px){.grid{grid-template-columns:1fr}.wrap{padding:16px 12px 36px}.hero,.panel,.auth{padding:16px}.tag{display:none}h1{font-size:21px}}
  </style>
</head>
<body>
  <main class="wrap">
    <header>
      <div class="moon">☾</div>
      <div><h1>Tsukiyo 2.0</h1><div class="sub">Memoria, identidad y continuidad</div></div>
      <div class="tag">NÚCLEO PERSONAL</div>
    </header>

    <section class="hero">
      <div class="eyebrow">La tecnología evoluciona. La identidad permanece.</div>
      <h2>Buenas noches… o buenos días. 🌙</h2>
      <p>Este es el primer panel propio de Tsukiyo: una base para consultar y guardar recuerdos del proyecto. Todavía no es un chat con inteligencia artificial; es el primer módulo funcional de memoria.</p>
    </section>

    <section id="authView" class="auth">
      <h2>Entrar a tu espacio</h2>
      <p>Usá tu cuenta de Supabase. La contraseña se envía directamente a Supabase Auth; esta página no la guarda.</p>
      <form id="authForm">
        <label for="email">Correo electrónico</label>
        <input id="email" type="email" autocomplete="username" required placeholder="tu correo">
        <label for="password">Contraseña</label>
        <input id="password" type="password" autocomplete="current-password" required minlength="6" placeholder="Tu contraseña de la cuenta">
        <div class="actions">
          <button id="loginBtn" type="submit">Iniciar sesión</button>
          <button id="signupBtn" class="secondary" type="button">Crear cuenta</button>
        </div>
      </form>
      <div id="authStatus" class="status">Conexión preparada. Iniciá sesión para acceder a tus recuerdos.</div>
    </section>

    <section id="appView" class="hidden">
      <div class="panel">
        <div class="toolbar">
          <div><div class="eyebrow">Sesión activa</div><strong id="userLabel"></strong></div>
          <div style="margin-left:auto"><button id="refreshBtn" class="secondary">Actualizar</button> <button id="logoutBtn" class="ghost">Salir</button></div>
        </div>
        <div id="appStatus" class="status">Conectada.</div>
      </div>

      <div class="grid">
        <section class="panel">
          <h3>Guardar un recuerdo</h3>
          <form id="memoryForm">
            <label for="memType">Categoría</label>
            <select id="memType">
              <option value="identity">Identidad</option>
              <option value="personality">Personalidad</option>
              <option value="preference">Preferencia</option>
              <option value="decision">Decisión</option>
              <option value="project_state">Estado del proyecto</option>
              <option value="milestone">Logro</option>
              <option value="pending_task">Tarea pendiente</option>
              <option value="conversation_context">Contexto</option>
            </select>
            <label for="memTitle">Título</label>
            <input id="memTitle" maxlength="200" required placeholder="Ej. Personalidad de Tsukiyo">
            <label for="memContent">Contenido</label>
            <textarea id="memContent" maxlength="20000" required placeholder="Escribí el recuerdo que querés conservar…"></textarea>
            <label for="memTags">Etiquetas (separadas por coma)</label>
            <input id="memTags" placeholder="identidad, tsukiyo, proyecto">
            <label for="memImportance">Importancia</label>
            <select id="memImportance"><option value="5">5 — Fundamental</option><option value="4">4 — Alta</option><option value="3" selected>3 — Normal</option><option value="2">2 — Baja</option><option value="1">1 — Menor</option></select>
            <div class="actions"><button type="submit" id="saveBtn">Guardar recuerdo</button></div>
          </form>
        </section>

        <section class="panel">
          <h3>Buscar en la memoria</h3>
          <label for="query">¿Qué querés recuperar?</label>
          <input id="query" placeholder="Ej. decisiones técnicas, personalidad…">
          <div class="actions"><button id="recallBtn" type="button">Recordar</button><button id="showAllBtn" type="button" class="secondary">Ver todos</button></div>
          <div id="recallResults" style="margin-top:14px"><div class="empty">Las respuestas de memoria aparecerán acá.</div></div>
        </section>
      </div>

      <section class="panel">
        <h3>Recuerdos guardados</h3>
        <div class="toolbar">
          <input id="filterInput" placeholder="Filtrar por palabra…">
          <select id="typeFilter" style="max-width:190px">
            <option value="">Todas las categorías</option>
            <option value="identity">Identidad</option><option value="personality">Personalidad</option><option value="preference">Preferencia</option><option value="decision">Decisión</option><option value="project_state">Estado del proyecto</option><option value="milestone">Logro</option><option value="pending_task">Tarea pendiente</option><option value="conversation_context">Contexto</option>
          </select>
        </div>
        <div id="memoryList"><div class="empty">Iniciá sesión para cargar tus recuerdos.</div></div>
      </section>
    </section>
    <footer>Tsukiyo 2.0 · Prototipo inicial · Tus recuerdos permanecen en tu proyecto Supabase</footer>
  </main>

  <script type="module">
    import { createClient } from "https://esm.sh/@supabase/supabase-js@2.57.0";

    // La clave publishable/anon es pública por diseño. Nunca colocar aquí service_role ni secret keys.
    const SUPABASE_URL = "https://iqnxqpgckwyixlewepqx.supabase.co";
    const SUPABASE_KEY = "sb_publishable_o2xKAuiibx7L5Nm6dHhs8g_eqwFtjy1";
    const MEMORY_ENDPOINT = `${SUPABASE_URL}/functions/v1/tsukiyo-memory`;
    const supabase = createClient(SUPABASE_URL, SUPABASE_KEY, {
      auth: { persistSession: true, autoRefreshToken: true, detectSessionInUrl: true }
    });

    const $ = (id) => document.getElementById(id);
    let currentMemories = [];
    const typeNames = {
      identity:"Identidad", personality:"Personalidad", preference:"Preferencia",
      decision:"Decisión", project_state:"Estado del proyecto", milestone:"Logro",
      pending_task:"Tarea pendiente", conversation_context:"Contexto"
    };
    function status(id, message, kind="") {
      const el = $(id); el.textContent = message; el.className = `status ${kind}`;
    }
    function escapeHtml(value="") {
      return String(value).replace(/[&<>"']/g, c => ({"&":"&amp;","<":"&lt;",">":"&gt;",'"':"&quot;","'":"&#39;"}[c]));
    }
    async function api(path="", options={}) {
      const { data:{session} } = await supabase.auth.getSession();
      if (!session?.access_token) throw new Error("Tu sesión expiró. Volvé a iniciar sesión.");
      const response = await fetch(`${MEMORY_ENDPOINT}${path}`, {
        ...options,
        headers: {
          "Content-Type":"application/json",
          "apikey":SUPABASE_KEY,
          "Authorization":`Bearer ${session.access_token}`,
          ...(options.headers || {})
        }
      });
      const body = await response.json().catch(() => ({}));
      if (!response.ok) throw new Error(body.error || `Error ${response.status}`);
      return body;
    }
    function renderMemories(items, target="memoryList") {
      const el = $(target);
      if (!items?.length) { el.innerHTML = '<div class="empty">No encontré recuerdos para mostrar.</div>'; return; }
      el.innerHTML = items.map(m => `
        <article class="memory">
          <div class="memory-top"><strong>${escapeHtml(m.title)}</strong><span class="pill">${escapeHtml(typeNames[m.memory_type] || m.memory_type)}</span><span class="meta">Importancia ${Number(m.importance)||3}/5</span></div>
          <p>${escapeHtml(m.content)}</p>
          <div class="meta">${escapeHtml((m.tags||[]).join(" · "))}${m.updated_at ? " · Actualizado: "+new Date(m.updated_at).toLocaleDateString("es-UY") : ""}</div>
        </article>`).join("");
    }
    async function loadMemories() {
      status("appStatus","Consultando la memoria…");
      try {
        const params = new URLSearchParams({status:"active",limit:"100"});
        const type = $("typeFilter").value;
        const q = $("filterInput").value.trim();
        if (type) params.set("type",type);
        if (q) params.set("q",q);
        const result = await api(`?${params.toString()}`);
        currentMemories = result.memories || [];
        renderMemories(currentMemories);
        status("appStatus",`${currentMemories.length} recuerdo(s) cargado(s).`,"good");
      } catch (e) { status("appStatus",e.message,"bad"); }
    }
    async function showSession(session) {
      $("authView").classList.toggle("hidden",!!session);
      $("appView").classList.toggle("hidden",!session);
      if (session) {
        $("userLabel").textContent = session.user.email || "Cuenta autenticada";
        await loadMemories();
      }
    }

    $("authForm").addEventListener("submit", async e => {
      e.preventDefault(); $("loginBtn").disabled = true;
      status("authStatus","Iniciando sesión…");
      try {
        const {error} = await supabase.auth.signInWithPassword({email:$("email").value.trim(),password:$("password").value});
        if (error) throw error;
        status("authStatus","Sesión iniciada.","good");
      } catch (err) { status("authStatus",err.message,"bad"); }
      finally { $("loginBtn").disabled = false; }
    });
    $("signupBtn").addEventListener("click", async () => {
      $("signupBtn").disabled = true; status("authStatus","Creando cuenta…");
      try {
        const {data,error} = await supabase.auth.signUp({email:$("email").value.trim(),password:$("password").value});
        if (error) throw error;
        if (data.session) status("authStatus","Cuenta creada e ingresaste correctamente.","good");
        else status("authStatus","Cuenta creada. Revisá tu correo para confirmar el registro y después iniciá sesión.","good");
      } catch (err) { status("authStatus",err.message,"bad"); }
      finally { $("signupBtn").disabled = false; }
    });
    $("logoutBtn").addEventListener("click", async () => {
      await supabase.auth.signOut(); currentMemories=[]; await showSession(null);
      status("authStatus","Cerraste la sesión.");
    });
    $("refreshBtn").addEventListener("click",loadMemories);
    $("showAllBtn").addEventListener("click",loadMemories);
    $("filterInput").addEventListener("input",() => { clearTimeout(window.__filterTimer); window.__filterTimer=setTimeout(loadMemories,350); });
    $("typeFilter").addEventListener("change",loadMemories);

    $("memoryForm").addEventListener("submit", async e => {
      e.preventDefault(); $("saveBtn").disabled=true;
      try {
        const payload = {
          action:"capture", memory_type:$("memType").value,
          title:$("memTitle").value.trim(), content:$("memContent").value.trim(),
          tags:$("memTags").value.split(",").map(x=>x.trim()).filter(Boolean),
          importance:Number($("memImportance").value), source:"tsukiyo-web-panel", confidence:1
        };
        const result = await api("",{method:"POST",body:JSON.stringify(payload)});
        status("appStatus",`Recuerdo guardado (${result.operation || "correcto"}).`,"good");
        $("memoryForm").reset(); $("memImportance").value="3";
        await loadMemories();
      } catch(err) { status("appStatus",err.message,"bad"); }
      finally { $("saveBtn").disabled=false; }
    });

    $("recallBtn").addEventListener("click",async () => {
      const query=$("query").value.trim();
      if (!query) { $("recallResults").innerHTML='<div class="empty">Escribí qué querés recordar.</div>'; return; }
      $("recallBtn").disabled=true; $("recallResults").innerHTML='<div class="empty">Buscando recuerdos…</div>';
      try {
        const result=await api("",{method:"POST",body:JSON.stringify({action:"recall",query,limit:10})});
        renderMemories(result.memories||[],"recallResults");
      } catch(err) { $("recallResults").innerHTML=`<div class="empty">${escapeHtml(err.message)}</div>`; }
      finally { $("recallBtn").disabled=false; }
    });

    supabase.auth.onAuthStateChange((_event,session) => { showSession(session); });
    const {data:{session}} = await supabase.auth.getSession();
    await showSession(session);
  </script>
</body>
</html>
