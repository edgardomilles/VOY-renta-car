import React from "react";
import { motion } from "framer-motion";
import { Car, CalendarClock, MapPin, ShieldCheck, Zap, Gauge, Phone } from "lucide-react";

// --- Mini sistema de diseño (paleta + tipografías) ---
// Paleta
// Primario: #0EA5E9 (Sky)
// Secundario: #0F172A (Slate-900)
// Acento: #22C55E (Green)
// Neutros: #F8FAFC (Slate-50), #1E293B (Slate-800)
// Tipografías: Headings — Inter/Tailwind font-sans; Cuerpo — system-ui

const Badge = ({ children }) => (
  <span className="inline-flex items-center rounded-full bg-sky-100 px-3 py-1 text-sky-700 text-xs font-semibold">
    {children}
  </span>
);

const Stat = ({ label, value }) => (
  <div className="rounded-2xl bg-white p-5 shadow-sm ring-1 ring-slate-100">
    <div className="text-3xl font-bold text-slate-900">{value}</div>
    <div className="mt-1 text-sm text-slate-500">{label}</div>
  </div>
);

const BookingWidget = () => (
  <div className="rounded-2xl bg-white p-5 shadow-xl ring-1 ring-slate-100 grid gap-3">
    <div className="grid grid-cols-1 md:grid-cols-2 gap-3">
      <label className="grid gap-1">
        <span className="text-sm text-slate-600">Retiro</span>
        <input type="date" className="rounded-xl border border-slate-200 p-3 outline-none focus:ring-2 focus:ring-sky-300" />
      </label>
      <label className="grid gap-1">
        <span className="text-sm text-slate-600">Devolución</span>
        <input type="date" className="rounded-xl border border-slate-200 p-3 outline-none focus:ring-2 focus:ring-sky-300" />
      </label>
      <label className="grid gap-1">
        <span className="text-sm text-slate-600">Hora</span>
        <input type="time" className="rounded-xl border border-slate-200 p-3 outline-none focus:ring-2 focus:ring-sky-300" />
      </label>
      <label className="grid gap-1">
        <span className="text-sm text-slate-600">Lugar</span>
        <select className="rounded-xl border border-slate-200 p-3 outline-none focus:ring-2 focus:ring-sky-300">
          <option>Aeropuerto Andrés Sabella (ANF)</option>
          <option>Oficina Centro</option>
          <option>Entrega a domicilio (Antofagasta)</option>
        </select>
      </label>
      <label className="grid gap-1 md:col-span-2">
        <span className="text-sm text-slate-600">Vehículo</span>
        <select className="rounded-xl border border-slate-200 p-3 outline-none focus:ring-2 focus:ring-sky-300">
          <option>Económico — Chevrolet Sail 2012</option>
        </select>
      </label>
    </div>
    <button className="mt-2 inline-flex items-center justify-center gap-2 rounded-2xl bg-sky-500 px-5 py-3 text-white font-semibold shadow hover:bg-sky-600 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-sky-400">
      <CalendarClock className="h-5 w-5" /> Buscar disponibilidad
    </button>
    <p className="text-xs text-slate-500">Confirmación inmediata por email y WhatsApp. Cancelación gratuita 24h antes.</p>
  </div>
);

const FleetCard = () => (
  <div className="grid gap-4 rounded-2xl bg-white p-5 shadow-xl ring-1 ring-slate-100">
    <div className="aspect-[16/9] rounded-xl bg-gradient-to-br from-sky-100 to-slate-100 flex items-center justify-center">
      <Car className="h-16 w-16 text-slate-500" />
    </div>
    <div className="flex items-start justify-between">
      <div>
        <h3 className="text-lg font-semibold text-slate-900">Chevrolet Sail 2012 — Económico</h3>
        <p className="text-sm text-slate-600">5 pasajeros · A/C · Maletero mediano · Manual</p>
      </div>
      <Badge>Desde $25.000/día</Badge>
    </div>
    <div className="flex flex-wrap items-center gap-3 text-sm text-slate-600">
      <span className="inline-flex items-center gap-1"><Gauge className="h-4 w-4"/>Eficiente</span>
      <span className="inline-flex items-center gap-1"><ShieldCheck className="h-4 w-4"/>Seguro incluido</span>
      <span className="inline-flex items-center gap-1"><Zap className="h-4 w-4"/>Entrega rápida</span>
    </div>
    <button className="inline-flex items-center justify-center gap-2 rounded-2xl bg-slate-900 px-5 py-3 text-white font-semibold hover:bg-slate-800">
      Reservar este vehículo
    </button>
  </div>
);

const Feature = ({ icon: Icon, title, desc }) => (
  <div className="rounded-2xl bg-white p-6 shadow-sm ring-1 ring-slate-100">
    <div className="flex items-center gap-3">
      <div className="rounded-xl bg-sky-100 p-2"><Icon className="h-5 w-5 text-sky-700"/></div>
      <h3 className="text-base font-semibold text-slate-900">{title}</h3>
    </div>
    <p className="mt-3 text-sm text-slate-600">{desc}</p>
  </div>
);

export default function VOYRentACarDesign() {
  return (
    <div className="min-h-screen bg-gradient-to-b from-slate-50 to-white">
      {/* NAV */}
      <header className="sticky top-0 z-30 backdrop-blur bg-white/70 border-b border-slate-200/60">
        <div className="mx-auto max-w-7xl px-4 py-3 flex items-center justify-between">
          <div className="flex items-center gap-3">
            <div className="h-9 w-9 rounded-2xl bg-sky-500"/>
            <div className="leading-tight">
              <div className="font-extrabold text-slate-900">VOY Rent a Car</div>
              <div className="text-xs text-slate-500">Antofagasta</div>
            </div>
          </div>
          <nav className="hidden md:flex items-center gap-6 text-sm text-slate-700">
            <a href="#flota" className="hover:text-slate-900">Flota</a>
            <a href="#precios" className="hover:text-slate-900">Tarifas</a>
            <a href="#reservar" className="hover:text-slate-900">Reservar</a>
            <a href="#contacto" className="hover:text-slate-900">Contacto</a>
          </nav>
          <button className="inline-flex items-center gap-2 rounded-2xl bg-slate-900 px-4 py-2 text-white text-sm font-semibold">
            <CalendarClock className="h-4 w-4"/> Reservar
          </button>
        </div>
      </header>

      {/* HERO */}
      <section className="relative overflow-hidden">
        <div className="absolute inset-0 -z-10 bg-gradient-to-br from-sky-50 via-white to-slate-100"/>
        <div className="mx-auto max-w-7xl px-4 py-14 grid md:grid-cols-2 gap-10 items-center">
          <motion.div initial={{ opacity: 0, y: 20 }} animate={{ opacity: 1, y: 0 }} transition={{ duration: 0.6 }}>
            <Badge>Reserva en 60 segundos</Badge>
            <h1 className="mt-4 text-4xl md:text-5xl font-extrabold tracking-tight text-slate-900">
              Arriendo de autos en Antofagasta <span className="text-sky-600">fácil y rápido</span>
            </h1>
            <p className="mt-4 text-slate-600 text-lg">
              Entrega en aeropuerto, hoteles o a domicilio. Seguro incluido y atención 24/7.
            </p>
            <div className="mt-6 flex flex-wrap items-center gap-3 text-sm text-slate-600">
              <span className="inline-flex items-center gap-1"><MapPin className="h-4 w-4"/>Aeropuerto Andrés Sabella</span>
              <span className="inline-flex items-center gap-1"><ShieldCheck className="h-4 w-4"/>Cobertura básica incluida</span>
              <span className="inline-flex items-center gap-1"><Zap className="h-4 w-4"/>Entrega en 15 min</span>
            </div>
          </motion.div>
          <motion.div id="reservar" initial={{ opacity: 0, y: 20 }} animate={{ opacity: 1, y: 0 }} transition={{ duration: 0.6, delay: 0.1 }}>
            <BookingWidget />
          </motion.div>
        </div>
      </section>

      {/* FEATURES */}
      <section className="mx-auto max-w-7xl px-4 py-8">
        <div className="grid md:grid-cols-3 gap-5">
          <Feature icon={Zap} title="Check-in express" desc="Firma digital y retiro sin filas." />
          <Feature icon={ShieldCheck} title="Seguro incluido" desc="Protección básica con opción full cobertura." />
          <Feature icon={MapPin} title="Entrega donde estés" desc="Aeropuerto, hotel u oficina en Antofagasta." />
        </div>
      </section>

      {/* FLEET */}
      <section id="flota" className="mx-auto max-w-7xl px-4 py-10">
        <div className="flex items-end justify-between">
          <div>
            <h2 className="text-2xl md:text-3xl font-extrabold text-slate-900">Flota disponible</h2>
            <p className="text-slate-600">Comienza con tu vehículo económico y escala cuando quieras.</p>
          </div>
        </div>
        <div className="mt-6 grid md:grid-cols-2 lg:grid-cols-3 gap-6">
          <FleetCard />
        </div>
      </section>

      {/* PRICING */}
      <section id="precios" className="mx-auto max-w-7xl px-4 py-10">
        <div className="rounded-2xl bg-gradient-to-br from-slate-900 to-slate-800 p-8 text-white">
          <div className="grid md:grid-cols-2 gap-6 items-center">
            <div>
              <h3 className="text-2xl font-extrabold">Tarifas transparentes</h3>
              <ul className="mt-4 space-y-2 text-slate-200 text-sm list-disc list-inside">
                <li>Desde $25.000/día (económico)</li>
                <li>Kilometraje justo · Combustible lleno/lleno</li>
                <li>Asistencia en ruta 24/7</li>
                <li>Descuento semanal y mensual</li>
              </ul>
            </div>
            <div className="rounded-2xl bg-white p-6 text-slate-900">
              <div className="flex items-baseline gap-2">
                <div className="text-4xl font-extrabold">$25.000</div>
                <div className="text-sm text-slate-500">/ día · Chevrolet Sail 2012</div>
              </div>
              <button className="mt-4 w-full rounded-2xl bg-sky-500 px-5 py-3 text-white font-semibold hover:bg-sky-600">Reservar ahora</button>
              <p className="mt-2 text-xs text-slate-500">Incluye IVA. Depósito reembolsable. Requisitos: cédula y licencia vigentes.</p>
            </div>
          </div>
        </div>
      </section>

      {/* TESTIMONIOS */}
      <section className="mx-auto max-w-7xl px-4 py-10">
        <div className="grid md:grid-cols-3 gap-5">
          {[
            {q: "Entrega rápida en el aeropuerto, 100% recomendado.", n: "María G."},
            {q: "Proceso simple y precio justo.", n: "Jorge A."},
            {q: "El auto en excelente estado, volveré a arrendar.", n: "Camila R."},
          ].map((t, i) => (
            <div key={i} className="rounded-2xl bg-white p-6 shadow-sm ring-1 ring-slate-100">
              <p className="text-slate-700">“{t.q}”</p>
              <div className="mt-3 text-sm text-slate-500">{t.n}</div>
            </div>
          ))}
        </div>
      </section>

      {/* FAQ */}
      <section className="mx-auto max-w-7xl px-4 py-10">
        <h2 className="text-2xl md:text-3xl font-extrabold text-slate-900">Preguntas frecuentes</h2>
        <div className="mt-6 grid md:grid-cols-2 gap-6">
          {[
            {q: "¿Qué necesito para arrendar?", a: "Cédula o pasaporte, licencia vigente y tarjeta para garantía."},
            {q: "¿Puedo recibir el auto en el aeropuerto?", a: "Sí, entregamos en ANF y también en hoteles u oficinas."},
            {q: "¿Incluye seguro?", a: "Incluye cobertura básica con opción de ampliar a todo riesgo."},
            {q: "¿Cómo pago?", a: "Pagos con tarjeta (WebPay/MercadoPago) o transferencia."},
          ].map((item, i) => (
            <div key={i} className="rounded-2xl bg-white p-6 shadow-sm ring-1 ring-slate-100">
              <div className="font-semibold text-slate-900">{item.q}</div>
              <div className="mt-2 text-sm text-slate-600">{item.a}</div>
            </div>
          ))}
        </div>
      </section>

      {/* FOOTER */}
      <footer id="contacto" className="bg-slate-900">
        <div className="mx-auto max-w-7xl px-4 py-10 text-slate-300">
          <div className="grid md:grid-cols-3 gap-8">
            <div>
              <div className="text-white font-extrabold text-lg">VOY Rent a Car</div>
              <p className="mt-2 text-sm text-slate-400">Antofagasta, Chile · Entrega en aeropuerto y a domicilio.</p>
            </div>
            <div className="grid gap-2 text-sm">
              <a href="#flota" className="hover:text-white">Flota</a>
              <a href="#precios" className="hover:text-white">Tarifas</a>
              <a href="#reservar" className="hover:text-white">Reservar</a>
            </div>
            <div className="grid gap-2 text-sm">
              <div className="inline-flex items-center gap-2"><Phone className="h-4 w-4"/> WhatsApp: agrega tu número</div>
              <div className="inline-flex items-center gap-2"><MapPin className="h-4 w-4"/> Aeropuerto ANF & Centro</div>
            </div>
          </div>
          <div className="mt-8 text-xs text-slate-500">© {new Date().getFullYear()} VOY Rent a Car. Todos los derechos reservados.</div>
        </div>
      </footer>
    </div>
  );
}
