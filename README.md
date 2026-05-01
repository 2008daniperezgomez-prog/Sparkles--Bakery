import { useEffect } from "react";
import { Button } from "@/components/ui/button";
import { Card } from "@/components/ui/card";
import { MapPin, Phone, Clock, Star, Coffee, Cake, Cookie, ShoppingBag } from "lucide-react";
import heroImage from "@/assets/hero-bakery.jpg";
import eclairsImg from "@/assets/eclairs.jpg";
import rainbowImg from "@/assets/rainbow-cake.jpg";
import frappeImg from "@/assets/frappe.jpg";

const Index = () => {
  useEffect(() => {
    document.title = "Sparkles Bakery | Cafetería y Repostería en Curridabat";
    const meta = document.querySelector('meta[name="description"]') || document.createElement("meta");
    meta.setAttribute("name", "description");
    meta.setAttribute("content", "Sparkles Bakery: cafetería y repostería artesanal en Cronos Plaza, Curridabat. Eclairs, tortas, café frappé y más. Consumo en el lugar, para llevar y entrega a domicilio.");
    document.head.appendChild(meta);
  }, []);

  const featured = [
    { name: "Eclairs Artesanales", desc: "Masa choux delicada rellena de crema pastelera y cubierta de chocolate.", img: eclairsImg },
    { name: "Torta Rainbow", desc: "Capas multicolor con un suave glaseado de queso crema. Nuestro clásico.", img: rainbowImg },
    { name: "Frappé de Caramelo", desc: "Café frío batido con caramelo, crema y un toque de dulzura.", img: frappeImg },
  ];

  const categories = [
    { icon: Coffee, title: "Cafés de Especialidad", text: "Espressos, cappuccinos y frappés preparados con grano costarricense." },
    { icon: Cake, title: "Tortas & Quequitos", text: "Red velvet, selva negra, rainbow y más. Por encargo o por porción." },
    { icon: Cookie, title: "Repostería Fina", text: "Eclairs, milhojas, tartaletas y opciones dulces y saladas." },
    { icon: ShoppingBag, title: "Para Llevar", text: "Pedí por teléfono y pasá recogiendo, o solicitá entrega a domicilio." },
  ];

  return (
    <div className="min-h-screen bg-background">
      {/* Nav */}
      <header className="fixed top-0 left-0 right-0 z-50 backdrop-blur-md bg-background/80 border-b border-border">
        <nav className="container mx-auto flex items-center justify-between py-4">
          <a href="#inicio" className="font-serif text-2xl font-bold text-primary">
            Sparkles<span className="text-accent">.</span>
          </a>
          <div className="hidden md:flex items-center gap-8 text-sm font-medium">
            <a href="#menu" className="hover:text-accent transition-colors">Menú</a>
            <a href="#nosotros" className="hover:text-accent transition-colors">Nosotros</a>
            <a href="#visita" className="hover:text-accent transition-colors">Visítanos</a>
            <a href="#contacto" className="hover:text-accent transition-colors">Contacto</a>
          </div>
          <Button asChild size="sm" className="bg-accent hover:bg-accent/90 text-accent-foreground">
            <a href="tel:+50640522130">Llamar</a>
          </Button>
        </nav>
      </header>

      {/* Hero */}
      <section id="inicio" className="relative h-screen flex items-center justify-center overflow-hidden">
        <img
          src={heroImage}
          alt="Vitrina de repostería con eclairs, torta rainbow y café frappé"
          width={1920}
          height={1080}
          className="absolute inset-0 w-full h-full object-cover"
        />
        <div className="absolute inset-0" style={{ background: "var(--gradient-hero)" }} />
        <div className="relative z-10 text-center px-6 max-w-4xl">
          <p className="text-accent uppercase tracking-[0.3em] text-sm mb-6 font-medium">
            Cafetería · Repostería · Curridabat
          </p>
          <h1 className="font-serif text-5xl md:text-7xl lg:text-8xl font-bold text-white mb-6 leading-tight">
            Dulces momentos,<br />
            <em className="text-gold font-normal">hechos a mano</em>
          </h1>
          <p className="text-lg md:text-xl text-white/90 mb-10 max-w-2xl mx-auto">
            Una experiencia de repostería artesanal y café de especialidad en el corazón de Cronos Plaza.
          </p>
          <div className="flex flex-wrap gap-4 justify-center">
            <Button asChild size="lg" className="bg-accent hover:bg-accent/90 text-accent-foreground shadow-warm">
              <a href="#menu">Ver el Menú</a>
            </Button>
            <Button asChild size="lg" variant="outline" className="bg-transparent border-white text-white hover:bg-white hover:text-primary">
              <a href="#visita">Cómo llegar</a>
            </Button>
          </div>
        </div>
      </section>

      {/* Categorías */}
      <section className="py-24 bg-gradient-cream">
        <div className="container mx-auto px-6">
          <div className="text-center max-w-2xl mx-auto mb-16">
            <p className="text-accent uppercase tracking-widest text-xs mb-3">Lo que ofrecemos</p>
            <h2 className="font-serif text-4xl md:text-5xl font-bold text-primary mb-4">
              Sabores que enamoran
            </h2>
            <p className="text-muted-foreground">
              Recetas cuidadas, ingredientes frescos y la calidez de un negocio local.
            </p>
          </div>
          <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6">
            {categories.map((c) => (
              <Card key={c.title} className="p-8 text-center bg-card hover:shadow-soft transition-all hover:-translate-y-1 border-border">
                <div className="inline-flex p-4 rounded-full bg-secondary mb-4">
                  <c.icon className="w-6 h-6 text-accent" />
                </div>
                <h3 className="font-serif text-xl font-semibold text-primary mb-2">{c.title}</h3>
                <p className="text-sm text-muted-foreground">{c.text}</p>
              </Card>
            ))}
          </div>
        </div>
      </section>

      {/* Menú destacado */}
      <section id="menu" className="py-24">
        <div className="container mx-auto px-6">
          <div className="text-center max-w-2xl mx-auto mb-16">
            <p className="text-accent uppercase tracking-widest text-xs mb-3">Nuestro menú</p>
            <h2 className="font-serif text-4xl md:text-5xl font-bold text-primary mb-4">
              Platos destacados
            </h2>
            <p className="text-muted-foreground">
              Las favoritas de quienes nos visitan, preparadas con dedicación cada día.
            </p>
          </div>
          <div className="grid grid-cols-1 md:grid-cols-3 gap-8">
            {featured.map((item) => (
              <article key={item.name} className="group">
                <div className="aspect-square overflow-hidden rounded-2xl mb-5 shadow-soft">
                  <img
                    src={item.img}
                    alt={item.name}
                    loading="lazy"
                    width={1024}
                    height={1024}
                    className="w-full h-full object-cover group-hover:scale-105 transition-transform duration-700"
                  />
                </div>
                <h3 className="font-serif text-2xl font-semibold text-primary mb-2">{item.name}</h3>
                <p className="text-muted-foreground">{item.desc}</p>
              </article>
            ))}
          </div>
        </div>
      </section>

      {/* Nosotros */}
      <section id="nosotros" className="py-24 bg-primary text-primary-foreground">
        <div className="container mx-auto px-6 grid md:grid-cols-2 gap-16 items-center">
          <div>
            <p className="text-gold uppercase tracking-widest text-xs mb-3">Nuestra historia</p>
            <h2 className="font-serif text-4xl md:text-5xl font-bold mb-6">
              Una pequeña cafetería con un gran corazón
            </h2>
            <p className="text-primary-foreground/80 mb-4 leading-relaxed">
              Sparkles Bakery nació con la idea de ofrecer repostería de excelente presentación y sabor en un ambiente cálido y cercano. Aunque nuestro local en Cronos Plaza es acogedor y de tamaño íntimo, ponemos toda la pasión en cada eclair, cada torta y cada taza de café que servimos.
            </p>
            <p className="text-primary-foreground/80 leading-relaxed">
              Aceptamos efectivo y tarjetas. Podés disfrutar en el lugar, llevar tus favoritos o llamarnos para encargar y pasar a recoger.
            </p>
          </div>
          <div className="grid grid-cols-2 gap-4">
            <div className="p-6 rounded-2xl bg-primary-foreground/5 border border-primary-foreground/10">
              <div className="flex items-center gap-1 mb-2">
                {[...Array(4)].map((_, i) => (
                  <Star key={i} className="w-4 h-4 fill-gold text-gold" />
                ))}
                <Star className="w-4 h-4 text-gold" />
              </div>
              <p className="font-serif text-3xl font-bold">4.1</p>
              <p className="text-sm text-primary-foreground/70">Calificación Google</p>
            </div>
            <div className="p-6 rounded-2xl bg-primary-foreground/5 border border-primary-foreground/10">
              <p className="font-serif text-3xl font-bold mb-1">+90</p>
              <p className="text-sm text-primary-foreground/70">Opiniones de clientes</p>
            </div>
            <div className="p-6 rounded-2xl bg-primary-foreground/5 border border-primary-foreground/10 col-span-2">
              <p className="italic text-primary-foreground/90 mb-3">
                "Deliciosos eclairs, opciones variadas de repostería salada y dulce. Productos con excelente presentación y sabor."
              </p>
              <p className="text-xs text-gold uppercase tracking-wider">— Adriana J., Local Guide</p>
            </div>
          </div>
        </div>
      </section>

      {/* Visítanos */}
      <section id="visita" className="py-24 bg-secondary">
        <div className="container mx-auto px-6">
          <div className="text-center max-w-2xl mx-auto mb-16">
            <p className="text-accent uppercase tracking-widest text-xs mb-3">Visítanos</p>
            <h2 className="font-serif text-4xl md:text-5xl font-bold text-primary mb-4">
              Te esperamos en Cronos Plaza
            </h2>
          </div>
          <div className="grid md:grid-cols-3 gap-6 max-w-5xl mx-auto">
            <Card className="p-8 bg-card text-center">
              <MapPin className="w-7 h-7 text-accent mx-auto mb-4" />
              <h3 className="font-serif text-lg font-semibold text-primary mb-2">Ubicación</h3>
              <p className="text-sm text-muted-foreground">
                Cronos Plaza, Carr. Vieja a Cartago<br />
                Curridabat, Pinares, San José
              </p>
            </Card>
            <Card className="p-8 bg-card text-center">
              <Phone className="w-7 h-7 text-accent mx-auto mb-4" />
              <h3 className="font-serif text-lg font-semibold text-primary mb-2">Llámanos</h3>
              <a href="tel:+50640522130" className="text-sm text-muted-foreground hover:text-accent transition-colors">
                4052 2130
              </a>
              <p className="text-xs text-muted-foreground mt-2">Pedidos y encargos</p>
            </Card>
            <Card className="p-8 bg-card text-center">
              <Clock className="w-7 h-7 text-accent mx-auto mb-4" />
              <h3 className="font-serif text-lg font-semibold text-primary mb-2">Horario</h3>
              <p className="text-sm text-muted-foreground">
                Abierto hoy<br />
                Cierra a las 7:00 p.m.
              </p>
            </Card>
          </div>
        </div>
      </section>

      {/* CTA Footer */}
      <footer id="contacto" className="bg-primary text-primary-foreground py-16">
        <div className="container mx-auto px-6 text-center">
          <h2 className="font-serif text-3xl md:text-4xl font-bold mb-4">
            ¿Listo para endulzar tu día?
          </h2>
          <p className="text-primary-foreground/70 mb-8 max-w-xl mx-auto">
            Llamanos para hacer tu pedido o pasá a visitarnos en Cronos Plaza.
          </p>
          <div className="flex flex-wrap gap-4 justify-center mb-12">
            <Button asChild size="lg" className="bg-accent hover:bg-accent/90 text-accent-foreground">
              <a href="tel:+50640522130">Llamar al 4052 2130</a>
            </Button>
            <Button asChild size="lg" variant="outline" className="bg-transparent border-primary-foreground/30 text-primary-foreground hover:bg-primary-foreground hover:text-primary">
              <a href="https://www.google.com/maps/search/?api=1&query=Sparkles+Bakery+Cronos+Plaza+Curridabat" target="_blank" rel="noopener noreferrer">
                Ver en Google Maps
              </a>
            </Button>
          </div>
          <div className="border-t border-primary-foreground/10 pt-8 text-sm text-primary-foreground/60">
            © {new Date().getFullYear()} Sparkles Bakery · Curridabat, Costa Rica
          </div>
        </div>
      </footer>
    </div>
  );
};

export default Index;
