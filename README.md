<html lang="es">

<head>

<meta charset="UTF-8">

<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Hueyitas – Refugio de Mascotas</title>

<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700;900&family=DM+Sans:wght@300;400;500;600&display=swap" rel="stylesheet">

<style>

  :root {

    --cream: #FDF6EC;

    --warm: #F5E6CC;

    --orange: #E8763A;

    --orange-dark: #C45A20;

    --brown: #5C3317;

    --brown-light: #8B5E3C;

    --green: #3D7A5A;

    --green-light: #5EAD81;

    --red: #C0392B;

    --text: #2C1A0E;

    --text-muted: #8B7355;

    --shadow: 0 4px 24px rgba(92,51,23,0.10);

  }

  * { box-sizing: border-box; margin: 0; padding: 0; }

  body { font-family: 'DM Sans', sans-serif; background: var(--cream); color: var(--text); min-height: 100vh; }



/* ──────────────── LOGIN PAGE ──────────────── */

#login-page {

min-height: 100vh;

background: linear-gradient(135deg, #5C3317 0%, #E8763A 60%, #FDF6EC 100%);

display: flex; align-items: center; justify-content: center;

position: relative; overflow: hidden;

}

#login-page::before {

content: ‘’;

position: absolute; inset: 0;

background: url(“data:image/svg+xml,%3Csvg width=‘60’ height=‘60’ viewBox=‘0 0 60 60’ xmlns=‘http://www.w3.org/2000/svg’%3E%3Cg fill=‘none’ fill-rule=‘evenodd’%3E%3Cg fill=’%23ffffff’ fill-opacity=‘0.04’%3E%3Ccircle cx=‘30’ cy=‘30’ r=‘10’/%3E%3C/g%3E%3C/g%3E%3C/svg%3E”);

pointer-events: none;

}

.login-card {

background: rgba(253,246,236,0.97);

border-radius: 28px;

padding: 52px 44px;

width: 420px;

max-width: 95vw;

box-shadow: 0 24px 80px rgba(92,51,23,0.35);

position: relative;

animation: slideUp 0.7s cubic-bezier(.16,1,.3,1) both;

}

@keyframes slideUp { from { opacity:0; transform: translateY(40px); } to { opacity:1; transform: translateY(0); } }

.login-logo { text-align: center; margin-bottom: 32px; }

.login-logo .paw { font-size: 52px; display: block; animation: bounce 2s infinite; }

@keyframes bounce { 0%,100% { transform: translateY(0); } 50% { transform: translateY(-8px); } }

.login-logo h1 { font-family: ‘Playfair Display’, serif; font-size: 2.6rem; color: var(–brown); line-height: 1; }

.login-logo p { color: var(–text-muted); font-size: 0.95rem; margin-top: 6px; letter-spacing: 0.05em; }

.form-group { margin-bottom: 20px; }

.form-group label { display: block; font-size: 0.82rem; font-weight: 600; color: var(–brown-light); text-transform: uppercase; letter-spacing: 0.07em; margin-bottom: 7px; }

.form-group input {

width: 100%; padding: 13px 16px; border: 2px solid var(–warm);

border-radius: 12px; font-family: ‘DM Sans’, sans-serif; font-size: 1rem;

background: #fff; color: var(–text); outline: none; transition: border 0.2s;

}

.form-group input:focus { border-color: var(–orange); }

.btn-login {

width: 100%; padding: 15px; background: var(–orange); color: #fff;

border: none; border-radius: 14px; font-family: ‘DM Sans’, sans-serif;

font-size: 1.05rem; font-weight: 600; cursor: pointer; letter-spacing: 0.04em;

transition: background 0.2s, transform 0.1s; margin-top: 8px;

}

.btn-login:hover { background: var(–orange-dark); transform: translateY(-1px); }

.login-footer { text-align: center; margin-top: 24px; font-size: 0.85rem; color: var(–text-muted); }



/* ──────────────── APP SHELL ──────────────── */

#app { display: none; min-height: 100vh; flex-direction: column; }

#app.visible { display: flex; }



/* NAV */

nav {

background: var(–brown);

padding: 0 32px;

display: flex; align-items: center; gap: 0;

box-shadow: 0 2px 12px rgba(92,51,23,0.18);

position: sticky; top: 0; z-index: 100;

}

.nav-brand {

font-family: ‘Playfair Display’, serif; font-size: 1.5rem; color: var(–cream);

display: flex; align-items: center; gap: 10px; padding: 18px 0; margin-right: 32px;

white-space: nowrap;

}

.nav-brand span { font-size: 1.4rem; }

.nav-links { display: flex; flex: 1; gap: 0; }

.nav-link {

padding: 20px 22px; color: rgba(253,246,236,0.7); font-size: 0.95rem; font-weight: 500;

cursor: pointer; border-bottom: 3px solid transparent;

transition: color 0.2s, border-color 0.2s; letter-spacing: 0.02em; user-select: none;

}

.nav-link:hover { color: var(–cream); }

.nav-link.active { color: var(–orange); border-bottom-color: var(–orange); }

.nav-user {

margin-left: auto; display: flex; align-items: center; gap: 12px;

color: rgba(253,246,236,0.8); font-size: 0.9rem;

}

.nav-avatar {

width: 36px; height: 36px; border-radius: 50%; background: var(–orange);

display: flex; align-items: center; justify-content: center;

font-weight: 700; color: #fff; font-size: 0.9rem; cursor: pointer;

}

.btn-logout {

background: rgba(255,255,255,0.12); border: none; color: rgba(253,246,236,0.75);

padding: 7px 14px; border-radius: 8px; font-size: 0.82rem; cursor: pointer;

transition: background 0.2s;

}

.btn-logout:hover { background: rgba(255,255,255,0.2); }



/* MAIN CONTENT */

main { flex: 1; padding: 36px 40px; max-width: 1100px; width: 100%; margin: 0 auto; }



/* ──────────────── SECTIONS ──────────────── */

.section { display: none; animation: fadeIn 0.4s ease; }

.section.active { display: block; }

@keyframes fadeIn { from { opacity:0; transform: translateY(12px); } to { opacity:1; transform: translateY(0); } }



/* SECTION HEADER */

.sec-header { margin-bottom: 32px; }

.sec-header h2 { font-family: ‘Playfair Display’, serif; font-size: 2rem; color: var(–brown); }

.sec-header p { color: var(–text-muted); margin-top: 6px; font-size: 0.95rem; }



/* CARDS GRID */

.cards-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(220px, 1fr)); gap: 22px; }

.pet-card {

background: #fff; border-radius: 20px; overflow: hidden;

box-shadow: var(–shadow); transition: transform 0.2s, box-shadow 0.2s;

cursor: pointer;

}

.pet-card:hover { transform: translateY(-4px); box-shadow: 0 10px 36px rgba(92,51,23,0.16); }

.pet-emoji { font-size: 3.4rem; text-align: center; padding: 24px 16px 12px; background: var(–warm); }

.pet-info { padding: 16px 18px; }

.pet-info h3 { font-size: 1.05rem; font-weight: 600; color: var(–brown); }

.pet-info .meta { font-size: 0.82rem; color: var(–text-muted); margin-top: 4px; }

.pet-badge {

display: inline-block; margin-top: 10px; padding: 4px 12px; border-radius: 20px;

font-size: 0.75rem; font-weight: 600; letter-spacing: 0.04em;

}

.badge-adopted { background: #E8F5E9; color: #2E7D32; }

.badge-waiting { background: #FFF3E0; color: #E65100; }

.badge-care { background: #E3F2FD; color: #1565C0; }



/* TABS */

.tab-bar { display: flex; gap: 4px; background: var(–warm); border-radius: 14px; padding: 5px; margin-bottom: 28px; width: fit-content; }

.tab-btn {

padding: 9px 22px; border-radius: 10px; border: none; cursor: pointer;

font-family: ‘DM Sans’, sans-serif; font-size: 0.9rem; font-weight: 500;

background: transparent; color: var(–text-muted); transition: all 0.2s;

}

.tab-btn.active { background: #fff; color: var(–brown); box-shadow: 0 2px 8px rgba(92,51,23,0.1); font-weight: 600; }



/* HORARIO */

.schedule-table { width: 100%; border-collapse: collapse; background: #fff; border-radius: 16px; overflow: hidden; box-shadow: var(–shadow); }

.schedule-table th { background: var(–brown); color: var(–cream); padding: 14px 18px; text-align: left; font-size: 0.85rem; letter-spacing: 0.05em; text-transform: uppercase; }

.schedule-table td { padding: 14px 18px; border-bottom: 1px solid var(–warm); font-size: 0.93rem; }

.schedule-table tr:last-child td { border-bottom: none; }

.schedule-table tr:hover td { background: var(–cream); }

.time-badge { background: var(–orange); color: #fff; padding: 3px 10px; border-radius: 8px; font-size: 0.8rem; font-weight: 600; }

.day-chip {

display: inline-block; background: var(–warm); color: var(–brown); padding: 3px 10px;

border-radius: 20px; font-size: 0.78rem; font-weight: 600; margin: 2px 3px 2px 0;

}



/* PERFIL */

.profile-card {

background: #fff; border-radius: 24px; padding: 40px; max-width: 560px;

box-shadow: var(–shadow);

}

.profile-avatar {

width: 80px; height: 80px; border-radius: 50%; background: linear-gradient(135deg, var(–orange), var(–brown));

display: flex; align-items: center; justify-content: center;

font-size: 2rem; color: #fff; margin-bottom: 28px;

}

.profile-field { margin-bottom: 20px; }

.profile-field label { font-size: 0.78rem; font-weight: 600; text-transform: uppercase; letter-spacing: 0.07em; color: var(–text-muted); display: block; margin-bottom: 5px; }

.profile-field .value { font-size: 1.02rem; color: var(–text); font-weight: 500; border-bottom: 2px solid var(–warm); padding-bottom: 8px; }

.profile-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 0 32px; }



/* WELCOME BANNER */

.welcome-banner {

background: linear-gradient(120deg, var(–brown) 0%, var(–orange) 100%);

border-radius: 24px; padding: 36px 40px; color: #fff; margin-bottom: 36px;

position: relative; overflow: hidden;

}

.welcome-banner::after {

content: ‘🐾’; position: absolute; right: 40px; top: 50%; transform: translateY(-50%);

font-size: 5rem; opacity: 0.18;

}

.welcome-banner h2 { font-family: ‘Playfair Display’, serif; font-size: 1.7rem; }

.welcome-banner p { opacity: 0.85; margin-top: 8px; font-size: 0.95rem; }



/* STATS ROW */

.stats-row { display: grid; grid-template-columns: repeat(3, 1fr); gap: 18px; margin-bottom: 32px; }

.stat-card { background: #fff; border-radius: 18px; padding: 24px 20px; box-shadow: var(–shadow); text-align: center; }

.stat-card .num { font-family: ‘Playfair Display’, serif; font-size: 2.4rem; color: var(–orange); }

.stat-card .lbl { font-size: 0.83rem; color: var(–text-muted); margin-top: 4px; font-weight: 500; }



/* RESPONSIVE */

@media (max-width: 640px) {

main { padding: 20px 16px; }

nav { padding: 0 14px; }

.nav-link { padding: 18px 12px; font-size: 0.85rem; }

.stats-row { grid-template-columns: 1fr 1fr; }

.profile-grid { grid-template-columns: 1fr; }

}

</style>



</head>

<body>



<!-- ═══════════════ LOGIN ═══════════════ -->



<div id="login-page">

  <div class="login-card">

    <div class="login-logo">

      <span class="paw">🐾</span>

      <h1>Hueyitas</h1>

      <p>Sistema de Gestión del Refugio</p>

    </div>

    <div class="form-group">

      <label>Usuario / Número de Empleado</label>

      <input type="text" id="inp-user" placeholder="Ej. EMP-0042" />

    </div>

    <div class="form-group">

      <label>Contraseña</label>

      <input type="password" id="inp-pass" placeholder="••••••••" />

    </div>

    <button class="btn-login" onclick="doLogin()">Iniciar Sesión</button>

    <div class="login-footer">Refugio Hueyitas © 2025 · Todos los derechos reservados</div>

  </div>

</div>



<!-- ═══════════════ APP ═══════════════ -->



<div id="app">

  <!-- NAV -->

  <nav>

    <div class="nav-brand"><span>🐾</span> Hueyitas</div>

    <div class="nav-links">

      <div class="nav-link active" onclick="showSection('mascotas', this)">Mascotas</div>

      <div class="nav-link" onclick="showSection('horarios', this)">Horarios</div>

      <div class="nav-link" onclick="showSection('perfil', this)">Mi Cuenta</div>

    </div>

    <div class="nav-user">

      <span id="nav-name">Miranda R.</span>

      <div class="nav-avatar" id="nav-avatar">MR</div>

      <button class="btn-logout" onclick="doLogout()">Cerrar sesión</button>

    </div>

  </nav>



  <main>



```

<!-- ──────── MASCOTAS ──────── -->

<div id="sec-mascotas" class="section active">

  <div class="sec-header">

    <h2>🐶 Mascotas del Refugio</h2>

    <p>Gestiona las mascotas adoptadas y las que siguen buscando un hogar</p>

  </div>



  <div class="tab-bar">

    <button class="tab-btn active" onclick="showPetTab('mis-mascotas', this)">Mis Mascotas a Cuidar</button>

    <button class="tab-btn" onclick="showPetTab('adoptadas', this)">Adoptadas</button>

    <button class="tab-btn" onclick="showPetTab('en-espera', this)">Buscando Hogar</button>

  </div>



  <!-- MIS MASCOTAS A CUIDAR -->

  <div id="tab-mis-mascotas" class="cards-grid">

    <div class="pet-card">

      <div class="pet-emoji">🐱</div>

      <div class="pet-info">

        <h3>Manchas</h3>

        <div class="meta">Gato · 2 años · Macho</div>

        <div class="meta">Habitación B-3</div>

        <span class="pet-badge badge-care">A tu cuidado</span>

      </div>

    </div>

    <div class="pet-card">

      <div class="pet-emoji">🐶</div>

      <div class="pet-info">

        <h3>Coco</h3>

        <div class="meta">Perro · 4 años · Hembra</div>

        <div class="meta">Habitación C-1</div>

        <span class="pet-badge badge-care">A tu cuidado</span>

      </div>

    </div>

    <div class="pet-card">

      <div class="pet-emoji">🐱</div>

      <div class="pet-info">

        <h3>Luna</h3>

        <div class="meta">Gata · 1 año · Hembra</div>

        <div class="meta">Habitación A-2</div>

        <span class="pet-badge badge-care">A tu cuidado</span>

      </div>

    </div>

    <div class="pet-card">

      <div class="pet-emoji">🐶</div>

      <div class="pet-info">

        <h3>Peludo</h3>

        <div class="meta">Perro · 3 años · Macho</div>

        <div class="meta">Habitación D-4</div>

        <span class="pet-badge badge-care">A tu cuidado</span>

      </div>

    </div>

    <div class="pet-card">

      <div class="pet-emoji">🐱</div>

      <div class="pet-info">

        <h3>Tigre</h3>

        <div class="meta">Gato · 5 años · Macho</div>

        <div class="meta">Habitación B-1</div>

        <span class="pet-badge badge-care">A tu cuidado</span>

      </div>

    </div>

    <div class="pet-card">

      <div class="pet-emoji">🐶</div>

      <div class="pet-info">

        <h3>Nube</h3>

        <div class="meta">Perro · 6 meses · Hembra</div>

        <div class="meta">Habitación A-5</div>

        <span class="pet-badge badge-care">A tu cuidado</span>

      </div>

    </div>

  </div>



  <!-- ADOPTADAS -->

  <div id="tab-adoptadas" class="cards-grid" style="display:none;">

    <div class="pet-card">

      <div class="pet-emoji">🐶</div>

      <div class="pet-info">

        <h3>Max</h3>

        <div class="meta">Perro · 2 años · Macho</div>

        <div class="meta">Adoptado: 10 Ene 2025</div>

        <span class="pet-badge badge-adopted">✔ Adoptado</span>

      </div>

    </div>

    <div class="pet-card">

      <div class="pet-emoji">🐱</div>

      <div class="pet-info">

        <h3>Misi</h3>

        <div class="meta">Gata · 3 años · Hembra</div>

        <div class="meta">Adoptada: 22 Feb 2025</div>

        <span class="pet-badge badge-adopted">✔ Adoptada</span>

      </div>

    </div>

    <div class="pet-card">

      <div class="pet-emoji">🐶</div>

      <div class="pet-info">

        <h3>Bruno</h3>

        <div class="meta">Perro · 5 años · Macho</div>

        <div class="meta">Adoptado: 3 Mar 2025</div>

        <span class="pet-badge badge-adopted">✔ Adoptado</span>

      </div>

    </div>

    <div class="pet-card">

      <div class="pet-emoji">🐱</div>

      <div class="pet-info">

        <h3>Caramelo</h3>

        <div class="meta">Gato · 1 año · Macho</div>

        <div class="meta">Adoptado: 15 Abr 2025</div>

        <span class="pet-badge badge-adopted">✔ Adoptado</span>

      </div>

    </div>

  </div>



  <!-- EN ESPERA -->

  <div id="tab-en-espera" class="cards-grid" style="display:none;">

    <div class="pet-card">

      <div class="pet-emoji">🐶</div>

      <div class="pet-info">

        <h3>Canela</h3>

        <div class="meta">Perro · 7 meses · Hembra</div>

        <div class="meta">En refugio desde Ene 2025</div>

        <span class="pet-badge badge-waiting">🔍 Buscando hogar</span>

      </div>

    </div>

    <div class="pet-card">

      <div class="pet-emoji">🐱</div>

      <div class="pet-info">

        <h3>Sombra</h3>

        <div class="meta">Gato · 4 años · Macho</div>

        <div class="meta">En refugio desde Feb 2025</div>

        <span class="pet-badge badge-waiting">🔍 Buscando hogar</span>

      </div>

    </div>

    <div class="pet-card">

      <div class="pet-emoji">🐶</div>

      <div class="pet-info">

        <h3>Rocky</h3>

        <div class="meta">Perro · 2 años · Macho</div>

        <div class="meta">En refugio desde Mar 2025</div>

        <span class="pet-badge badge-waiting">🔍 Buscando hogar</span>

      </div>

    </div>

    <div class="pet-card">

      <div class="pet-emoji">🐱</div>

      <div class="pet-info">

        <h3>Bolita</h3>

        <div class="meta">Gata · 8 meses · Hembra</div>

        <div class="meta">En refugio desde Mar 2025</div>

        <span class="pet-badge badge-waiting">🔍 Buscando hogar</span>

      </div>

    </div>

    <div class="pet-card">

      <div class="pet-emoji">🐶</div>

      <div class="pet-info">

        <h3>Chispas</h3>

        <div class="meta">Perro · 1 año · Hembra</div>

        <div class="meta">En refugio desde Abr 2025</div>

        <span class="pet-badge badge-waiting">🔍 Buscando hogar</span>

      </div>

    </div>

  </div>

</div>



<!-- ──────── HORARIOS ──────── -->

<div id="sec-horarios" class="section">

  <div class="sec-header">

    <h2>🕐 Mis Horarios</h2>

    <p>Tu turno y los horarios asignados para el cuidado de cada mascota</p>

  </div>



  <div class="welcome-banner" style="margin-bottom:28px; padding:24px 32px;">

    <h2 style="font-size:1.2rem;">Turno Asignado: <strong>Matutino</strong></h2>

    <p>Lunes a Viernes · 07:00 – 14:00 hrs · Área: Habitaciones A y B</p>

  </div>



  <table class="schedule-table">

    <thead>

      <tr>

        <th>Mascota</th>

        <th>Tipo</th>

        <th>Actividad</th>

        <th>Hora</th>

        <th>Días</th>

      </tr>

    </thead>

    <tbody>

      <tr>

        <td>🐱 Manchas</td>

        <td>Gato</td>

        <td>Alimentación y limpieza</td>

        <td><span class="time-badge">07:30</span></td>

        <td><span class="day-chip">Lun</span><span class="day-chip">Mié</span><span class="day-chip">Vie</span></td>

      </tr>

      <tr>

        <td>🐶 Coco</td>

        <td>Perro</td>

        <td>Paseo matutino</td>

        <td><span class="time-badge">08:00</span></td>

        <td><span class="day-chip">Lun</span><span class="day-chip">Mar</span><span class="day-chip">Jue</span></td>

      </tr>

      <tr>

        <td>🐱 Luna</td>

        <td>Gata</td>

        <td>Alimentación y medicamento</td>

        <td><span class="time-badge">08:30</span></td>

        <td><span class="day-chip">Mar</span><span class="day-chip">Jue</span></td>

      </tr>

      <tr>

        <td>🐶 Peludo</td>

        <td>Perro</td>

        <td>Baño semanal</td>

        <td><span class="time-badge">09:00</span></td>

        <td><span class="day-chip">Mié</span></td>

      </tr>

      <tr>

        <td>🐱 Tigre</td>

        <td>Gato</td>

        <td>Revisión veterinaria</td>

        <td><span class="time-badge">10:00</span></td>

        <td><span class="day-chip">Lun</span></td>

      </tr>

      <tr>

        <td>🐶 Nube</td>

        <td>Perro</td>

        <td>Socialización y juego</td>

        <td><span class="time-badge">10:30</span></td>

        <td><span class="day-chip">Mar</span><span class="day-chip">Vie</span></td>

      </tr>

      <tr>

        <td>🐱 Manchas</td>

        <td>Gato</td>

        <td>Limpieza de habitación</td>

        <td><span class="time-badge">11:00</span></td>

        <td><span class="day-chip">Mar</span><span class="day-chip">Jue</span></td>

      </tr>

      <tr>

        <td>🐶 Coco</td>

        <td>Perro</td>

        <td>Alimentación tarde</td>

        <td><span class="time-badge">13:00</span></td>

        <td><span class="day-chip">Lun</span><span class="day-chip">Mié</span><span class="day-chip">Vie</span></td>

      </tr>

    </tbody>

  </table>

</div>



<!-- ──────── PERFIL ──────── -->

<div id="sec-perfil" class="section">

  <div class="sec-header">

    <h2>👤 Mi Cuenta</h2>

    <p>Información personal del empleado</p>

  </div>

  <div class="profile-card">

    <div class="profile-avatar">👩</div>

    <div class="profile-grid">

      <div class="profile-field">

        <label>Nombre Completo</label>

        <div class="value" id="pf-nombre">Miranda Ramírez López</div>

      </div>

      <div class="profile-field">

        <label>Número de Empleado</label>

        <div class="value" id="pf-emp">EMP-0042</div>

      </div>

      <div class="profile-field">

        <label>Fecha de Nacimiento</label>

        <div class="value" id="pf-fecha">14 de marzo de 1998</div>

      </div>

      <div class="profile-field">

        <label>CURP</label>

        <div class="value" id="pf-curp">RALE980314MDFMRN06</div>

      </div>

    </div>

    <div class="profile-field">

      <label>Dirección</label>

      <div class="value" id="pf-dir">Calle Girasoles #14, Col. Jardines, Guadalajara, Jalisco</div>

    </div>

  </div>

</div>

```



  </main>

</div>



<script>

  // ──── DATA ────

  const USER = {

    nombre: 'Miranda Ramírez López',

    empleado: 'EMP-0042',

    nacimiento: '14 de marzo de 1998',

    curp: 'RALE980314MDFMRN06',

    direccion: 'Calle Girasoles #14, Col. Jardines, Guadalajara, Jalisco',

    initials: 'MR',

    display: 'Miranda R.'

  };



  // ──── LOGIN ────

  function doLogin() {

    const u = document.getElementById('inp-user').value.trim();

    const p = document.getElementById('inp-pass').value.trim();

    if (!u || !p) { alert('Por favor ingresa tus credenciales.'); return; }



    document.getElementById('login-page').style.display = 'none';

    const app = document.getElementById('app');

    app.classList.add('visible');



    document.getElementById('nav-name').textContent = USER.display;

    document.getElementById('nav-avatar').textContent = USER.initials;

    document.getElementById('pf-nombre').textContent = USER.nombre;

    document.getElementById('pf-emp').textContent = USER.empleado;

    document.getElementById('pf-fecha').textContent = USER.nacimiento;

    document.getElementById('pf-curp').textContent = USER.curp;

    document.getElementById('pf-dir').textContent = USER.direccion;

  }



  document.getElementById('inp-pass').addEventListener('keydown', e => { if (e.key === 'Enter') doLogin(); });



  function doLogout() {

    document.getElementById('app').classList.remove('visible');

    document.getElementById('login-page').style.display = 'flex';

    document.getElementById('inp-user').value = '';

    document.getElementById('inp-pass').value = '';

    showSection('mascotas', document.querySelector('.nav-link'));

  }



  // ──── NAVIGATION ────

  function showSection(id, el) {

    document.querySelectorAll('.section').forEach(s => s.classList.remove('active'));

    document.querySelectorAll('.nav-link').forEach(l => l.classList.remove('active'));

    document.getElementById('sec-' + id).classList.add('active');

    el.classList.add('active');

  }



  // ──── PET TABS ────

  function showPetTab(id, el) {

    ['mis-mascotas','adoptadas','en-espera'].forEach(t => {

      document.getElementById('tab-' + t).style.display = 'none';

    });

    document.querySelectorAll('.tab-btn').forEach(b => b.classList.remove('active'));

    document.getElementById('tab-' + id).style.display = 'grid';

    el.classList.add('active');

  }

</script>



</body>

</html>

