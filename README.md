import { useState } from "react";

export default function GuestListSite() {
  const [formData, setFormData] = useState({
    name: "",
    phone: "",
    dob: "",
  });

  const handleChange = (e) => {
    setFormData({ ...formData, [e.target.name]: e.target.value });
  };

  const handleSubmit = (e) => {
    e.preventDefault();

    const payload = {
      ...formData,
      event: "Caribe Night",
    };

    console.log("ISCRIZIONE:", payload);

    alert("Sei stato inserito in lista per CARIBE NIGHT!");

    setFormData({
      name: "",
      phone: "",
      dob: "",
    });
  };

  return (
    <div className="min-h-screen flex items-center justify-center p-6 bg-gradient-to-br from-pink-500 via-yellow-400 via-orange-400 to-sky-400">
      
      <div className="w-full max-w-xl bg-black/40 backdrop-blur-2xl border border-white/20 rounded-3xl p-8 text-white shadow-2xl">

        <h1 className="text-5xl font-black text-center">CARIBE NIGHT</h1>
        <p className="text-center text-white/80 mb-8 mt-2">
          Official Guest List
        </p>

        <form onSubmit={handleSubmit} className="space-y-4">

          <input
            name="name"
            value={formData.name}
            onChange={handleChange}
            placeholder="Nome e Cognome"
            className="w-full p-4 rounded-2xl bg-black/30 border border-white/20"
            required
          />

          <input
            name="phone"
            value={formData.phone}
            onChange={handleChange}
            placeholder="Telefono"
            className="w-full p-4 rounded-2xl bg-black/30 border border-white/20"
            required
          />

          <input
            type="date"
            name="dob"
            value={formData.dob}
            onChange={handleChange}
            className="w-full p-4 rounded-2xl bg-black/30 border border-white/20"
            required
          />

          <div className="text-sm text-white/70">
            Evento fisso: <strong>Caribe Night</strong>
          </div>

          <button
            type="submit"
            className="w-full bg-white text-black font-black py-4 rounded-2xl hover:scale-[1.02] transition"
          >
            ENTRA IN LISTA
          </button>

        </form>
      </div>
    </div>
  );
}
