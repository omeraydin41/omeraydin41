<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ömer Aydın - Software Architect Portfolio</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: #0a0e27;
            color: #fff;
            overflow-x: hidden;
        }

        /* Animated Background */
        .bg-animation {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            z-index: -1;
        }

        .bg-animation::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: 
                radial-gradient(circle at 20% 50%, rgba(120, 119, 198, 0.3), transparent 50%),
                radial-gradient(circle at 80% 80%, rgba(102, 126, 234, 0.3), transparent 50%),
                radial-gradient(circle at 40% 20%, rgba(118, 75, 162, 0.3), transparent 50%);
            animation: bgShift 15s ease-in-out infinite;
        }

        @keyframes bgShift {
            0%, 100% { transform: scale(1) rotate(0deg); }
            50% { transform: scale(1.1) rotate(5deg); }
        }

        .container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 20px;
        }

        /* Hero Section */
        .hero {
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            position: relative;
        }

        .glitch-wrapper {
            width: 100%;
            height: 100px;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-bottom: 30px;
        }

        .glitch {
            font-size: 5rem;
            font-weight: 900;
            text-transform: uppercase;
            position: relative;
            text-shadow: 0.05em 0 0 #00fffc, -0.03em -0.04em 0 #fc00ff,
                0.025em 0.04em 0 #fffc00;
            animation: glitch 725ms infinite;
        }

        @keyframes glitch {
            0% {
                text-shadow: 0.05em 0 0 #00fffc, -0.03em -0.04em 0 #fc00ff,
                    0.025em 0.04em 0 #fffc00;
            }
            15% {
                text-shadow: 0.05em 0 0 #00fffc, -0.03em -0.04em 0 #fc00ff,
                    0.025em 0.04em 0 #fffc00;
            }
            16% {
                text-shadow: -0.05em -0.025em 0 #00fffc, 0.025em 0.035em 0 #fc00ff,
                    -0.05em -0.05em 0 #fffc00;
            }
            49% {
                text-shadow: -0.05em -0.025em 0 #00fffc, 0.025em 0.035em 0 #fc00ff,
                    -0.05em -0.05em 0 #fffc00;
            }
            50% {
                text-shadow: 0.05em 0.035em 0 #00fffc, 0.03em 0 0 #fc00ff,
                    0 -0.04em 0 #fffc00;
            }
            99% {
                text-shadow: 0.05em 0.035em 0 #00fffc, 0.03em 0 0 #fc00ff,
                    0 -0.04em 0 #fffc00;
            }
            100% {
                text-shadow: -0.05em 0 0 #00fffc, -0.025em -0.04em 0 #fc00ff,
                    -0.04em -0.025em 0 #fffc00;
            }
        }

        .subtitle {
            font-size: 1.8rem;
            margin-bottom: 2rem;
            opacity: 0;
            animation: fadeInUp 1s ease 0.3s forwards;
            background: linear-gradient(90deg, #00fffc, #fc00ff);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .badges {
            display: flex;
            gap: 20px;
            flex-wrap: wrap;
            justify-content: center;
            opacity: 0;
            animation: fadeInUp 1s ease 0.6s forwards;
        }

        .badge {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            padding: 12px 30px;
            border-radius: 50px;
            font-size: 1.1rem;
            font-weight: 600;
            border: 2px solid rgba(255, 255, 255, 0.3);
            transition: all 0.3s ease;
        }

        .badge:hover {
            background: rgba(255, 255, 255, 0.2);
            transform: translateY(-5px);
            box-shadow: 0 10px 30px rgba(0, 255, 252, 0.3);
        }

        @keyframes fadeInUp {
            to {
                opacity: 1;
                transform: translateY(0);
            }
            from {
                opacity: 0;
                transform: translateY(30px);
            }
        }

        /* About Section */
        .about-section {
            min-height: 100vh;
            padding: 80px 20px;
            background: rgba(0, 0, 0, 0.3);
        }

        .section-title {
            text-align: center;
            font-size: 3.5rem;
            margin-bottom: 3rem;
            font-weight: 700;
            background: linear-gradient(90deg, #00fffc, #fc00ff);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .about-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 50px;
            align-items: center;
        }

        .about-text {
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(10px);
            border: 2px solid rgba(255, 255, 255, 0.1);
            border-radius: 20px;
            padding: 40px;
        }

        .about-text h3 {
            font-size: 2rem;
            margin-bottom: 20px;
            color: #00fffc;
        }

        .about-text p {
            font-size: 1.1rem;
            line-height: 1.8;
            margin-bottom: 20px;
            color: rgba(255, 255, 255, 0.9);
        }

        .tech-stack {
            display: flex;
            flex-wrap: wrap;
            gap: 15px;
            margin-top: 30px;
        }

        .tech-item {
            background: linear-gradient(135deg, rgba(0, 255, 252, 0.2), rgba(252, 0, 255, 0.2));
            padding: 10px 20px;
            border-radius: 10px;
            border: 1px solid rgba(255, 255, 255, 0.2);
            font-weight: 600;
            transition: all 0.3s ease;
        }

        .tech-item:hover {
            transform: scale(1.1);
            box-shadow: 0 5px 20px rgba(0, 255, 252, 0.4);
        }

        .code-window {
            background: #1e1e1e;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.5);
        }

        .code-header {
            background: #323233;
            padding: 10px 15px;
            display: flex;
            gap: 8px;
            align-items: center;
        }

        .code-dot {
            width: 12px;
            height: 12px;
            border-radius: 50%;
        }

        .code-dot:nth-child(1) { background: #ff5f56; }
        .code-dot:nth-child(2) { background: #ffbd2e; }
        .code-dot:nth-child(3) { background: #27c93f; }

        .code-body {
            padding: 20px;
            font-family: 'Courier New', monospace;
            font-size: 0.95rem;
            line-height: 1.6;
            max-height: 500px;
            overflow-y: auto;
        }

        .code-keyword { color: #569cd6; }
        .code-class { color: #4ec9b0; }
        .code-string { color: #ce9178; }
        .code-comment { color: #6a9955; font-style: italic; }

        /* Microservices Architecture Section */
        .microservices-section {
            min-height: 100vh;
            padding: 80px 20px;
            background: rgba(0, 0, 0, 0.2);
        }

        .architecture-container {
            position: relative;
            padding: 60px 20px;
        }

        .api-gateway {
            position: relative;
            margin: 0 auto 80px;
            max-width: 400px;
            background: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
            padding: 30px 50px;
            border-radius: 15px;
            font-weight: 700;
            font-size: 1.5rem;
            box-shadow: 0 10px 40px rgba(245, 87, 108, 0.5);
            text-align: center;
            animation: pulse 2s ease-in-out infinite;
        }

        @keyframes pulse {
            0%, 100% {
                transform: scale(1);
            }
            50% {
                transform: scale(1.05);
            }
        }

        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            margin-bottom: 80px;
        }

        .service {
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(10px);
            border: 2px solid rgba(255, 255, 255, 0.1);
            border-radius: 20px;
            padding: 30px;
            text-align: center;
            transition: all 0.4s ease;
            cursor: pointer;
            position: relative;
            overflow: hidden;
        }

        .service::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(0, 255, 252, 0.2), transparent);
            transition: left 0.5s;
        }

        .service:hover::before {
            left: 100%;
        }

        .service:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 60px rgba(0, 255, 252, 0.3);
            border-color: #00fffc;
        }

        .service-icon {
            font-size: 3rem;
            margin-bottom: 15px;
            display: block;
            filter: drop-shadow(0 0 10px rgba(0, 255, 252, 0.5));
        }

        .service h3 {
            font-size: 1.5rem;
            margin-bottom: 10px;
            color: #00fffc;
        }

        .service p {
            font-size: 0.95rem;
            opacity: 0.8;
            line-height: 1.6;
        }

        /* Communication Lines */
        .communication-layer {
            text-align: center;
            margin: 60px 0;
        }

        .comm-tech {
            display: inline-flex;
            gap: 30px;
            flex-wrap: wrap;
            justify-content: center;
        }

        .comm-item {
            background: linear-gradient(135deg, rgba(252, 0, 255, 0.2), rgba(255, 252, 0, 0.2));
            padding: 15px 30px;
            border-radius: 15px;
            border: 2px solid rgba(252, 0, 255, 0.3);
            font-weight: 600;
            font-size: 1.1rem;
        }

        /* Database Layer */
        .database-layer {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
            margin-top: 60px;
        }

        .database {
            background: rgba(0, 0, 0, 0.3);
            border: 2px solid rgba(255, 255, 255, 0.2);
            border-radius: 15px;
            padding: 30px;
            text-align: center;
            animation: float 3s ease-in-out infinite;
            transition: all 0.3s ease;
        }

        .database:hover {
            border-color: #00fffc;
            transform: translateY(-10px);
        }

        .database:nth-child(2) {
            animation-delay: 0.5s;
        }

        .database:nth-child(3) {
            animation-delay: 1s;
        }

        @keyframes float {
            0%, 100% {
                transform: translateY(0);
            }
            50% {
                transform: translateY(-15px);
            }
        }

        .database-icon {
            font-size: 3rem;
            margin-bottom: 15px;
        }

        .database h4 {
            font-size: 1.3rem;
            color: #00fffc;
            margin-bottom: 10px;
        }

        /* Benefits Grid */
        .benefits {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            margin-top: 60px;
        }

        .benefit-card {
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(10px);
            border-radius: 15px;
            padding: 30px;
            border: 2px solid rgba(255, 255, 255, 0.1);
            transition: all 0.3s ease;
        }

        .benefit-card:hover {
            background: rgba(255, 255, 255, 0.1);
            transform: scale(1.02);
            border-color: #fc00ff;
        }

        .benefit-card h4 {
            font-size: 1.3rem;
            margin-bottom: 15px;
            color: #fc00ff;
        }

        .benefit-card p {
            opacity: 0.9;
            line-height: 1.6;
        }

        @media (max-width: 768px) {
            .glitch {
                font-size: 3rem;
            }
            
            .about-content {
                grid-template-columns: 1fr;
            }
            
            .services-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <div class="bg-animation"></div>

    <div class="hero">
        <div class="glitch-wrapper">
            <div class="glitch">ÖMER AYDIN</div>
        </div>
        <p class="subtitle">Software Architect & Backend Developer</p>
        <div class="badges">
            <div class="badge">🎓 YBS 3. Sınıf</div>
            <div class="badge">💻 .NET Developer</div>
            <div class="badge">🏗️ Microservices Expert</div>
        </div>
    </div>

    <div class="about-section">
        <div class="container">
            <h2 class="section-title">Hakkımda</h2>
            <div class="about-content">
                <div class="about-text">
                    <h3>🚀 Yazılım Mimarisi Tutkunu</h3>
                    <p>
                        Merhaba! Ben Ömer Aydın, <strong>Yönetim Bilişim Sistemleri</strong> 3. sınıf öğrencisiyim. 
                        Modern yazılım geliştirme pratiklerine ve özellikle <strong>mikroservis mimarisine</strong> tutkuyla bağlıyım.
                    </p>
                    <p>
                        <strong>C#</strong> ve <strong>.NET ekosistemi</strong> ile ölçeklenebilir, bakımı kolay ve performanslı 
                        enterprise uygulamalar geliştiriyorum. ASP.NET Core ile RESTful API'ler, Entity Framework Core ile 
                        veritabanı yönetimi, SignalR ile gerçek zamanlı uygulamalar ve gRPC ile yüksek performanslı 
                        servisler arası iletişim konularında deneyim sahibiyim.
                    </p>
                    <p>
                        Mikroservis mimarisi ile monolitik yapıların getirdiği sınırlamaları aşarak, her servisi bağımsız 
                        olarak deploy edebilen, ölçeklendirebilen ve teknoloji stack'ini seçebilen modern yazılım çözümleri 
                        üretiyorum. Docker konteynerizasyonu, Kubernetes orkestasyonu ve CI/CD pipeline'ları ile DevOps 
                        kültürünü benimsiyorum.
                    </p>
                    
                    <div class="tech-stack">
                        <div class="tech-item">C# 12</div>
                        <div class="tech-item">.NET 8</div>
                        <div class="tech-item">ASP.NET Core</div>
                        <div class="tech-item">Entity Framework</div>
                        <div class="tech-item">LINQ</div>
                        <div class="tech-item">Async/Await</div>
                        <div class="tech-item">Dependency Injection</div>
                        <div class="tech-item">RESTful APIs</div>
                        <div class="tech-item">gRPC</div>
                        <div class="tech-item">SignalR</div>
                        <div class="tech-item">SQL Server</div>
                        <div class="tech-item">PostgreSQL</div>
                        <div class="tech-item">MongoDB</div>
                        <div class="tech-item">Redis Cache</div>
                        <div class="tech-item">RabbitMQ</div>
                        <div class="tech-item">Docker</div>
                        <div class="tech-item">Kubernetes</div>
                        <div class="tech-item">Azure</div>
                    </div>
                </div>

                <div class="code-window">
                    <div class="code-header">
                        <div class="code-dot"></div>
                        <div class="code-dot"></div>
                        <div class="code-dot"></div>
                    </div>
                    <div class="code-body">
<span class="code-comment">// Mikroservis Örneği - Product Service</span>

<span class="code-keyword">using</span> Microsoft.AspNetCore.Mvc;
<span class="code-keyword">using</span> Microsoft.EntityFrameworkCore;

<span class="code-keyword">namespace</span> ProductService.API;

[<span class="code-class">ApiController</span>]
[<span class="code-class">Route</span>(<span class="code-string">"api/[controller]"</span>)]
<span class="code-keyword">public class</span> <span class="code-class">ProductsController</span> : <span class="code-class">ControllerBase</span>
{
    <span class="code-keyword">private readonly</span> <span class="code-class">IProductService</span> _productService;
    <span class="code-keyword">private readonly</span> <span class="code-class">IMessagePublisher</span> _messagePublisher;
    
    <span class="code-keyword">public</span> ProductsController(
        <span class="code-class">IProductService</span> productService,
        <span class="code-class">IMessagePublisher</span> messagePublisher)
    {
        _productService = productService;
        _messagePublisher = messagePublisher;
    }

    [<span class="code-class">HttpPost</span>]
    <span class="code-keyword">public async</span> <span class="code-class">Task</span>&lt;<span class="code-class">IActionResult</span>&gt; CreateProduct(
        [<span class="code-class">FromBody</span>] <span class="code-class">ProductDto</span> productDto)
    {
        <span class="code-keyword">var</span> product = <span class="code-keyword">await</span> _productService
            .CreateProductAsync(productDto);
        
        <span class="code-comment">// Event-Driven Communication</span>
        <span class="code-keyword">await</span> _messagePublisher.PublishAsync(
            <span class="code-keyword">new</span> <span class="code-class">ProductCreatedEvent</span> 
            { 
                ProductId = product.Id,
                Name = product.Name,
                Price = product.Price 
            });
        
        <span class="code-keyword">return</span> CreatedAtAction(
            nameof(GetProduct), 
            <span class="code-keyword">new</span> { id = product.Id }, 
            product);
    }

    [<span class="code-class">HttpGet</span>(<span class="code-string">"{id}"</span>)]
    [<span class="code-class">ResponseCache</span>(Duration = <span class="code-string">60</span>)]
    <span class="code-keyword">public async</span> <span class="code-class">Task</span>&lt;<span class="code-class">IActionResult</span>&gt; GetProduct(<span class="code-keyword">int</span> id)
    {
        <span class="code-keyword">var</span> product = <span class="code-keyword">await</span> _productService
            .GetProductByIdAsync(id);
        
        <span class="code-keyword">return</span> product == <span class="code-keyword">null</span> 
            ? NotFound() 
            : Ok(product);
    }
}
                    </div>
                </div>
            </div>
        </div>
    </div>

    <div class="microservices-section">
        <div class="container">
            <h2 class="section-title">🏗️ Mikroservis Mimarisi</h2>
            
            <div class="architecture-container">
                <div class="api-gateway">
                    🌐 API Gateway
                    <div style="font-size: 0.9rem; font-weight: 400; margin-top: 10px;">
                        Ocelot / YARP
                    </div>
                </div>

                <div class="services-grid">
                    <div class="service">
                        <span class="service-icon">👤</span>
                        <h3>Identity Service</h3>
                        <p>JWT Authentication, OAuth2.0, IdentityServer4 ile güvenli kullanıcı yönetimi ve yetkilendirme</p>
                    </div>
                    
                    <div class="service">
                        <span class="service-icon">📦</span>
                        <h3>Product Service</h3>
                        <p>Ürün katalog yönetimi, CQRS pattern, MediatR ile command/query separation</p>
                    </div>
                    
                    <div class="service">
                        <span class="service-icon">🛒</span>
                        <h3>Order Service</h3>
                        <p>Sipariş yönetimi, Saga pattern ile distributed transactions, Outbox pattern</p>
                    </div>
                    
                    <div class="service">
                        <span class="service-icon">💳</span>
                        <h3>Payment Service</h3>
                        <p>Ödeme işlemleri, PCI-DSS compliance, retry ve circuit breaker patterns</p>
                    </div>
                    
                    <div class="service">
                        <span class="service-icon">📊</span>
                        <h3>Inventory Service</h3>
                        <p>Stok takibi, event sourcing, gerçek zamanlı envanter güncellemeleri</p>
                    </div>
                    
                    <div class="service">
                        <span class="service-icon">📧</span>
                        <h3>Notification Service</h3>
                        <p>Email/SMS servisi, message queue (RabbitMQ), asenkron işleme</p>
                    </div>
                </div>

                <div class="communication-layer">
                    <h3 style="margin-bottom: 20px; color: #00fffc;">⚡ Servisler Arası İletişim</h3>
                    <div class="comm-tech">
                        <div class="comm-item">🔄 REST API</div>
                        <div class="comm-item">⚡ gRPC</div>
                        <div class="comm-item">📨 RabbitMQ</div>
                        <div class="comm-item">📡 SignalR</div>
                        <div class="comm-item">🔔 Event Bus</div>
                    </div>
                </div>

                <div class="database-layer">
                    <div class="database">
                        <div class="database-icon">🗄️</div>
                        <h4>SQL Server</h4>
                        <p>Transactional data, Entity Framework Core, ACID compliance</p>
                    </div>
                    <div class="database">
                        <div class="database-icon">🍃</div>
                        <h4>MongoDB</h4>
                        <p>Product catalog, flexible schema, high performance reads</p>
                    </div>
                    <div class="database">
                        <div class="database-icon">⚡</div>
                        <h4>Redis</h4>
                        <p>Distributed caching, session management, pub/sub messaging</p>
                    </div>
                </div>
            </div>

            <div class="benefits">
                <div class="benefit-card">
                    <h4>⚡ Bağımsız Ölçeklendirme</h4>
                    <p>Her mikroservis, yük durumuna göre ayrı ayrı ölçeklendirilebilir. Kubernetes HPA ile otomatik scaling sağlanır.</p>
                </div>
                <div class="benefit-card">
                    <h4>🔧 Teknoloji Özgürlüğü</h4>
                    <p>Her servis kendi ihtiyacına göre farklı database, framework veya teknoloji kullanabilir. Polyglot persistence desteklenir.</p>
                </div>
                <div class="benefit-card">
                    <h4>🚀 Hızlı Deployment</h4>
                    <p>CI/CD pipeline ile her servis bağımsız deploy edilir. Blue-green ve canary deployment stratejileri uygulanır.</p>
                </div>
                <div class="benefit-card">
                    <h4>🛡️ Fault Isolation</h4>
                    <p>Circuit breaker, retry ve bulkhead patterns ile hata izolasyonu. Bir servisin çökmesi diğerlerini etkilemez.</p>
                </div>
                <div class="benefit-card">
                    <h4>👥 Takım Bağımsızlığı</h4>
                    <p>Her mikroservis farklı takımlar tarafından geliştirilebilir. Domain-Driven Design ile iş mantığı ayrıştırılır.</p>
                </div>
                <div class="benefit-card">
                    <h4>📈 Continuous Evolution</h4>
                    <p>Servisler birbirini beklemeden güncellenebilir. API versioning ile backward compatibility sağlanır.</p>
                </div>
            </div>
        </div>
    </div>

    <script>
        // Scroll reveal animation
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        }, observerOptions);

        document.querySelectorAll('.service, .benefit-card, .database, .about-text, .code-window').forEach(el => {
            el.style.opacity = '0';
            el.style.transform = 'translateY(30px)';
            el.style.transition = 'all 0.6s ease';
            observer.observe(el);
        });

        // Interactive service highlighting
        const services = document.querySelectorAll('.service');
        services.forEach(service => {
            service.addEventListener('mouseenter', () => {
                services.forEach(s => {
                    if (s !== service)


