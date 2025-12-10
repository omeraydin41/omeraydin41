import React, { useState, useEffect } from 'react';
import { Code, Database, Search, TestTube, GitBranch, Server, Mail, Linkedin, Github, Globe, Zap } from 'lucide-react';

export default function GitHubReadme() {
  const [typedText, setTypedText] = useState('');
  const fullText = 'Yönetim Bilişim Sistemleri Uzmanı';
  
  useEffect(() => {
    let index = 0;
    const timer = setInterval(() => {
      if (index <= fullText.length) {
        setTypedText(fullText.slice(0, index));
        index++;
      } else {
        clearInterval(timer);
      }
    }, 100);
    return () => clearInterval(timer);
  }, []);

  const technologies = [
    { name: 'C#', icon: Code, color: 'from-purple-500 to-purple-700' },
    { name: 'SQL', icon: Database, color: 'from-blue-500 to-blue-700' },
    { name: 'Elasticsearch', icon: Search, color: 'from-yellow-500 to-yellow-700' },
    { name: 'Unity', icon: TestTube, color: 'from-gray-700 to-gray-900' },
    { name: 'DevOps', icon: GitBranch, color: 'from-green-500 to-green-700' },
    { name: 'Microservices', icon: Server, color: 'from-red-500 to-red-700' }
  ];

  return (
    <div className="min-h-screen bg-gradient-to-br from-gray-900 via-blue-900 to-purple-900 p-8">
      <div className="max-w-4xl mx-auto space-y-8">
        
        {/* Header Banner */}
        <div className="relative overflow-hidden rounded-2xl bg-gradient-to-r from-blue-600 via-purple-600 to-pink-600 p-1">
          <div className="bg-gray-900 rounded-xl p-8 text-center">
            <div className="flex justify-center mb-4">
              <Zap className="w-16 h-16 text-yellow-400 animate-pulse" />
            </div>
            <h1 className="text-5xl font-bold text-white mb-4">
              👋 Merhaba, Ben <span className="bg-gradient-to-r from-blue-400 to-purple-400 bg-clip-text text-transparent">Developer</span>
            </h1>
            <p className="text-2xl text-gray-300 h-8">
              {typedText}<span className="animate-pulse">|</span>
            </p>
          </div>
        </div>

        {/* About Section */}
        <div className="bg-gray-800 rounded-xl p-6 border border-gray-700">
          <h2 className="text-3xl font-bold text-white mb-4 flex items-center">
            <Code className="mr-3 text-blue-400" /> Hakkımda
          </h2>
          <p className="text-gray-300 text-lg leading-relaxed">
            Microservices mimarisi ve enterprise çözümler konusunda uzmanlaşmış bir yazılım geliştiriciyim. 
            C# ve .NET ekosistemi ile scalable sistemler geliştiriyor, DevOps süreçlerini optimize ediyor 
            ve modern teknolojilerle yüksek performanslı uygulamalar tasarlıyorum.
          </p>
        </div>

        {/* Tech Stack */}
        <div className="bg-gray-800 rounded-xl p-6 border border-gray-700">
          <h2 className="text-3xl font-bold text-white mb-6 flex items-center">
            <Server className="mr-3 text-purple-400" /> Teknoloji Yığınım
          </h2>
          <div className="grid grid-cols-2 md:grid-cols-3 gap-4">
            {technologies.map((tech, index) => {
              const Icon = tech.icon;
              return (
                <div
                  key={index}
                  className={`bg-gradient-to-br ${tech.color} rounded-lg p-4 transform hover:scale-105 transition-all duration-300 cursor-pointer shadow-lg hover:shadow-2xl`}
                >
                  <div className="flex items-center justify-center mb-2">
                    <Icon className="w-8 h-8 text-white" />
                  </div>
                  <p className="text-white text-center font-semibold">{tech.name}</p>
                </div>
              );
            })}
          </div>
        </div>

        {/* Skills Detail */}
        <div className="bg-gray-800 rounded-xl p-6 border border-gray-700">
          <h2 className="text-3xl font-bold text-white mb-6">🎯 Uzmanlık Alanlarım</h2>
          <div className="space-y-4">
            <div className="bg-gray-700 rounded-lg p-4">
              <h3 className="text-xl font-semibold text-blue-400 mb-2">Backend Development</h3>
              <p className="text-gray-300">C#, ASP.NET Core, Web API, Entity Framework, LINQ</p>
            </div>
            <div className="bg-gray-700 rounded-lg p-4">
              <h3 className="text-xl font-semibold text-purple-400 mb-2">Microservices Architecture</h3>
              <p className="text-gray-300">Distributed Systems, Message Queues, Service Discovery, API Gateway</p>
            </div>
            <div className="bg-gray-700 rounded-lg p-4">
              <h3 className="text-xl font-semibold text-green-400 mb-2">DevOps & CI/CD</h3>
              <p className="text-gray-300">Docker, Kubernetes, Azure DevOps, Git, Automated Testing</p>
            </div>
            <div className="bg-gray-700 rounded-lg p-4">
              <h3 className="text-xl font-semibold text-yellow-400 mb-2">Database & Search</h3>
              <p className="text-gray-300">SQL Server, Elasticsearch, Database Design, Query Optimization</p>
            </div>
          </div>
        </div>

        {/* GitHub Stats */}
        <div className="bg-gray-800 rounded-xl p-6 border border-gray-700">
          <h2 className="text-3xl font-bold text-white mb-6 flex items-center">
            <Github className="mr-3 text-gray-400" /> GitHub İstatistiklerim
          </h2>
          <div className="space-y-4">
            <div className="bg-gray-700 rounded-lg p-4 text-center">
              <p className="text-gray-400 text-sm mb-2">GitHub Stats</p>
              <code className="text-green-400 text-xs block bg-gray-800 p-2 rounded">
                ![GitHub Stats](https://github-readme-stats.vercel.app/api?username=KULLANICI_ADIN&show_icons=true&theme=tokyonight)
              </code>
            </div>
            <div className="bg-gray-700 rounded-lg p-4 text-center">
              <p className="text-gray-400 text-sm mb-2">Most Used Languages</p>
              <code className="text-green-400 text-xs block bg-gray-800 p-2 rounded">
                ![Top Langs](https://github-readme-stats.vercel.app/api/top-langs/?username=KULLANICI_ADIN&layout=compact&theme=tokyonight)
              </code>
            </div>
            <div className="bg-gray-700 rounded-lg p-4 text-center">
              <p className="text-gray-400 text-sm mb-2">GitHub Streak</p>
              <code className="text-green-400 text-xs block bg-gray-800 p-2 rounded">
                ![GitHub Streak](https://github-readme-streak-stats.herokuapp.com/?user=KULLANICI_ADIN&theme=tokyonight)
              </code>
            </div>
          </div>
        </div>

        {/* Contact */}
        <div className="bg-gradient-to-r from-blue-600 to-purple-600 rounded-xl p-6">
          <h2 className="text-3xl font-bold text-white mb-6 text-center">📫 Benimle İletişime Geçin</h2>
          <div className="flex flex-wrap justify-center gap-4">
            <a href="mailto:email@example.com" className="bg-white hover:bg-gray-100 text-gray-900 px-6 py-3 rounded-lg flex items-center gap-2 transition-all transform hover:scale-105">
              <Mail className="w-5 h-5" />
              <span className="font-semibold">Email</span>
            </a>
            <a href="https://linkedin.com/in/kullanici" className="bg-white hover:bg-gray-100 text-gray-900 px-6 py-3 rounded-lg flex items-center gap-2 transition-all transform hover:scale-105">
              <Linkedin className="w-5 h-5" />
              <span className="font-semibold">LinkedIn</span>
            </a>
            <a href="https://github.com/kullanici" className="bg-white hover:bg-gray-100 text-gray-900 px-6 py-3 rounded-lg flex items-center gap-2 transition-all transform hover:scale-105">
              <Github className="w-5 h-5" />
              <span className="font-semibold">GitHub</span>
            </a>
          </div>
        </div>

        {/* Footer */}
        <div className="text-center text-gray-400 text-sm">
          <p>⭐ Star vermeyi unutmayın! | 💼 Açık işbirliğine hazırım</p>
        </div>

      </div>
    </div>
  );
}
