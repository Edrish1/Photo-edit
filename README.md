# Photo-edit// HomePage.js
import React, { useState } from 'react';
import './HomePage.css';

const tools = [
  {
    id: 'enhancer',
    title: 'AI Photo Enhancer',
    description: 'Convert low-quality photos to high-resolution. Sharpen blurry photos using AI.',
    icon: '🖼️',
  },
  {
    id: 'background',
    title: 'Background Remover/Changer',
    description: 'Remove background and add white, colored or custom background.',
    icon: '✂️',
  },
  {
    id: 'pdf',
    title: 'Image to PDF Converter',
    description: 'Convert one or more images to a PDF file. Customize page size and orientation.',
    icon: '📄',
  },
  {
    id: 'faceswap',
    title: 'AI Face Swap/Editor',
    description: 'Swap faces or convert to cartoon/anime style.',
    icon: '😊',
  },
  {
    id: 'collage',
    title: 'Photo Collage Maker',
    description: 'Create creative collages with multiple photos using templates.',
    icon: '🖼️🖼️',
  },
  {
    id: 'filters',
    title: 'Photo Filters & Editors',
    description: 'Brightness, contrast, RGB adjustment and more.',
    icon: '🎨',
  },
];

export default function HomePage() {
  const [activeTool, setActiveTool] = useState(null);
  const selectedTool = tools.find((tool) => tool.id === activeTool);

  return (
    <div className="homepage">
      {/* Logo Section */}
      <header className="logo-section">
        <img src="/logo.png" alt="AI Photo Editor" className="logo" />
      </header>

      {/* Top Ad Space */}
      <div className="ad top-ad">Ad Space Top</div>

      {/* Tools Grid */}
      <main className="tools-grid">
        {tools.map((tool) => (
          <div
            key={tool.id}
            className="tool-card"
            role="button"
            tabIndex={0}
            onClick={() => setActiveTool(tool.id)}
            onKeyDown={(e) => {
              if (e.key === 'Enter') {
                setActiveTool(tool.id);
              }
            }}
          >
            <span className="icon">{tool.icon}</span>
            <h3>{tool.title}</h3>
            <p>{tool.description}</p>
          </div>
        ))}
      </main>

      {/* Selected Tool Detail */}
      {selectedTool && (
        <section className="tool-detail">
          <h2>{selectedTool.title}</h2>
          <p>{selectedTool.description}</p>
        </section>
      )}

      {/* Bottom Ad Space */}
      <div className="ad bottom-ad">Ad Space Bottom</div>
    </div>
  );
}
