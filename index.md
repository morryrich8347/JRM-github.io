---
layout : defalit
title : 홈
----
#환영합니다.
jekyll로 만든 테마입니다.


<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8" />
  <title>문현준 · Portfolio</title>
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <style>
    :root {
      --bg-deep: #020617;
      --bg-main: #020617;
      --accent: #38bdf8;
      --accent-soft: #0ea5e9;
      --accent-strong: #22d3ee;
      --text-main: #f9fafb;
      --text-muted: #9ca3af;
      --card-bg: rgba(15, 23, 42, 0.9);
      --border-subtle: rgba(148, 163, 184, 0.35);
      --shadow-soft: 0 20px 40px rgba(15, 23, 42, 0.8);
      --radius-xl: 24px;
      --radius-lg: 18px;
      --transition-fast: 180ms ease-out;
      --transition-slow: 260ms ease-out;
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    html, body {
      height: 100%;
      scroll-behavior: smooth;
    }

    body {
      font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI",
        sans-serif;
      color: var(--text-main);
      background: radial-gradient(circle at 10% 0%, #1d2748 0, #020617 55%, #000 100%);
      position: relative;
      overflow-x: hidden;
    }

    /* ----- Space Background (Stars + Gradient Orbits) ----- */
    .space-background {
      position: fixed;
      inset: 0;
      z-index: -2;
      pointer-events: none;
      overflow: hidden;
    }

    .stars,
    .stars::before,
    .stars::after {
      position: absolute;
      content: "";
      width: 2px;
      height: 2px;
      background: transparent;
      box-shadow:
        50vw 10vh #e5e7eb,
        10vw 20vh #e5e7eb,
        30vw 40vh #e5e7eb,
        70vw 30vh #e5e7eb,
        90vw 60vh #e5e7eb,
        20vw 70vh #e5e7eb,
        60vw 80vh #e5e7eb,
        80vw 15vh #e5e7eb;
      animation: twinkle 8s linear infinite;
    }

    .stars::before {
      transform: translate3d(-40vw, -20vh, 0);
      box-shadow:
        15vw 30vh #f9fafb,
        45vw 55vh #f9fafb,
        65vw 10vh #f9fafb,
        85vw 45vh #f9fafb,
        25vw 85vh #f9fafb;
      animation-delay: -4s;
    }

    .stars::after {
      transform: translate3d(30vw, 30vh, 0);
      box-shadow:
        5vw 50vh #e5e7eb,
        35vw 75vh #e5e7eb,
        55vw 20vh #e5e7eb,
        75vw 65vh #e5e7eb;
      animation-delay: -2s;
    }

    @keyframes twinkle {
      0%, 100% { opacity: 0.6; transform: translate3d(0, 0, 0) scale(1); }
      50% { opacity: 1; transform: translate3d(0, -10px, 0) scale(1.1); }
    }

    .orb {
      position: absolute;
      border-radius: 999px;
      filter: blur(40px);
      opacity: 0.28;
      mix-blend-mode: screen;
      pointer-events: none;
    }

    .orb.orb-1 {
      width: 420px;
      height: 420px;
      background: radial-gradient(circle at 30% 30%, #38bdf8, transparent 65%);
      top: -80px;
      left: -40px;
      animation: float-orb-1 16s ease-in-out infinite;
    }

    .orb.orb-2 {
      width: 480px;
      height: 480px;
      background: radial-gradient(circle at 60% 60%, #0ea5e9, transparent 70%);
      bottom: -120px;
      right: -60px;
      animation: float-orb-2 20s ease-in-out infinite;
    }

    @keyframes float-orb-1 {
      0%, 100% { transform: translate3d(0, 0, 0); }
      50% { transform: translate3d(20px, 30px, 0); }
    }

    @keyframes float-orb-2 {
      0%, 100% { transform: translate3d(0, 0, 0); }
      50% { transform: translate3d(-20px, -40px, 0); }
    }

    /* ----- Layout ----- */
    .page-shell {
      position: relative;
      min-height: 100vh;
      display: flex;
      flex-direction: column;
    }

    header {
      position: sticky;
      top: 0;
      z-index: 10;
      backdrop-filter: blur(16px);
      background: linear-gradient(
        to bottom,
        rgba(15, 23, 42, 0.92),
        rgba(15, 23, 42, 0.7),
        transparent
      );
      border-bottom: 1px solid rgba(148, 163, 184, 0.25);
    }

    .nav {
      max-width: 1080px;
      margin: 0 auto;
      padding: 14px 20px 10px;
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 16px;
    }

    .logo {
      display: inline-flex;
      align-items: center;
      gap: 10px;
      padding: 6px 12px;
      border-radius: 999px;
      background: radial-gradient(circle at 0% 0%, rgba(56, 189, 248, 0.3), rgba(15, 23, 42, 0.8));
      border: 1px solid rgba(148, 163, 184, 0.4);
      box-shadow: 0 12px 30px rgba(15, 23, 42, 0.9);
      transform: translateY(0);
      transition: transform var(--transition-slow), box-shadow var(--transition-slow);
    }

    .logo:hover {
      transform: translateY(-2px);
      box-shadow: 0 18px 40px rgba(15, 23, 42, 1);
    }

    .logo-mark {
      width: 26px;
      height: 26px;
      border-radius: 999px;
      background: conic-gradient(from 210deg, #38bdf8, #22d3ee, #0f172a, #38bdf8);
      padding: 1px;
      display: inline-flex;
      align-items: center;
      justify-content: center;
    }

    .logo-mark-inner {
      width: 100%;
      height: 100%;
      border-radius: inherit;
      background: radial-gradient(circle at 30% 20%, #e5faff, #0f172a 70%);
      box-shadow: inset 0 0 10px rgba(15, 23, 42, 0.9);
    }

    .logo-text {
      display: flex;
      flex-direction: column;
      line-height: 1.2;
    }

    .logo-name {
      font-size: 0.86rem;
      font-weight: 600;
      letter-spacing: 0.05em;
      text-transform: uppercase;
    }

    .logo-role {
      font-size: 0.72rem;
      color: var(--text-muted);
    }

    .nav-links {
      display: flex;
      align-items: center;
      gap: 10px;
      font-size: 0.85rem;
    }

    .nav-links a {
      position: relative;
      padding: 6px 10px;
      border-radius: 999px;
      text-decoration: none;
      color: var(--text-muted);
      transition: color var(--transition-fast), background var(--transition-fast),
        transform var(--transition-fast), box-shadow var(--transition-fast);
    }

    .nav-links a::after {
      content: "";
      position: absolute;
      left: 50%;
      bottom: 4px;
      width: 0;
      height: 1px;
      border-radius: 999px;
      background: linear-gradient(to right, #38bdf8, #22d3ee);
      transform: translateX(-50%);
      transition: width var(--transition-fast);
    }

    .nav-links a:hover {
      color: var(--text-main);
      background: rgba(15, 23, 42, 0.8);
      transform: translateY(-1px);
      box-shadow: 0 8px 18px rgba(15, 23, 42, 0.8);
    }

    .nav-links a:hover::after {
      width: 60%;
    }

    .nav-cta {
      padding: 7px 13px;
      border-radius: 999px;
      border: 1px solid rgba(56, 189, 248, 0.9);
      background: radial-gradient(circle at 0 0, rgba(56, 189, 248, 0.35), rgba(15, 23, 42, 0.95));
      color: var(--text-main);
      font-weight: 500;
      letter-spacing: 0.03em;
      box-shadow: 0 10px 22px rgba(8, 47, 73, 0.9);
      cursor: pointer;
      transform: translateY(0) scale(1);
      transition: transform var(--transition-fast), box-shadow var(--transition-fast),
        background var(--transition-fast), border-color var(--transition-fast);
    }

    .nav-cta:hover {
      transform: translateY(-1px) scale(1.02);
      box-shadow: 0 16px 30px rgba(8, 47, 73, 1);
      background: radial-gradient(circle at 0 0, rgba(56, 189, 248, 0.9), rgba(15, 23, 42, 0.95));
    }

    .nav-cta:active {
      transform: translateY(1px) scale(0.98);
      box-shadow: 0 6px 14px rgba(8, 47, 73, 0.9);
      background: radial-gradient(circle at 20% 0, rgba(56, 189, 248, 0.6), rgba(15, 23, 42, 1));
    }

    /* ----- Main Content ----- */
    main {
      flex: 1;
    }

    .content {
      max-width: 1080px;
      margin: 0 auto;
      padding: 32px 20px 48px;
      display: flex;
      flex-direction: column;
      gap: 40px;
    }

    /* Hero Section */
    .hero {
      position: relative;
      margin-top: 10px;
      padding: 28px 22px;
      border-radius: var(--radius-xl);
      background:
        radial-gradient(circle at 10% 0%, rgba(56, 189, 248, 0.1), transparent 60%),
        radial-gradient(circle at 90% 100%, rgba(14, 165, 233, 0.2), transparent 60%),
        rgba(15, 23, 42, 0.96);
      border: 1px solid rgba(148, 163, 184, 0.45);
      box-shadow: 0 26px 60px rgba(15, 23, 42, 0.95);
      display: grid;
      grid-template-columns: minmax(0, 3.5fr) minmax(0, 2.5fr);
      gap: 28px;
      overflow: hidden;
    }

    .hero-orbit {
      position: absolute;
      inset: -40%;
      background:
        radial-gradient(circle at 20% 20%, rgba(56, 189, 248, 0.2), transparent 55%),
        radial-gradient(circle at 80% 80%, rgba(56, 189, 248, 0.25), transparent 55%);
      opacity: 0.15;
      mix-blend-mode: screen;
    }

    .hero-gradient-ring {
      position: absolute;
      width: 280px;
      height: 280px;
      border-radius: 999px;
      border: 1px solid rgba(56, 189, 248, 0.5);
      opacity: 0.5;
      right: -90px;
      top: 20%;
      transform: translateZ(0);
      animation: rotate-ring 28s linear infinite;
    }

    .hero-gradient-ring::after {
      content: "";
      position: absolute;
      inset: 28px;
      border-radius: inherit;
      border: 1px dashed rgba(148, 163, 184, 0.5);
      opacity: 0.8;
    }

    @keyframes rotate-ring {
      0% { transform: translateZ(0) rotate(0deg); }
      100% { transform: translateZ(0) rotate(360deg); }
    }

    .hero-left {
      position: relative;
      z-index: 1;
      display: flex;
      flex-direction: column;
      gap: 18px;
    }

    .hero-tag {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      padding: 6px 10px;
      border-radius: 999px;
      background: rgba(15, 23, 42, 0.9);
      border: 1px solid rgba(148, 163, 184, 0.7);
      font-size: 0.78rem;
      color: var(--text-muted);
      text-transform: uppercase;
      letter-spacing: 0.08em;
      backdrop-filter: blur(12px);
    }

    .hero-tag-dot {
      width: 8px;
      height: 8px;
      border-radius: 999px;
      background: radial-gradient(circle at 40% 30%, #38bdf8, #0ea5e9);
      box-shadow: 0 0 12px rgba(56, 189, 248, 0.9);
      animation: pulse-dot 1.6s ease-out infinite;
    }

    @keyframes pulse-dot {
      0%, 100% { transform: scale(1); opacity: 1; }
      50% { transform: scale(1.4); opacity: 0.5; }
    }

    .hero-title {
      font-size: clamp(1.9rem, 3.4vw, 2.4rem);
      line-height: 1.1;
      font-weight: 700;
      letter-spacing: -0.02em;
    }

    .hero-title span {
      display: block;
      background: linear-gradient(to right, #e5f5ff, #38bdf8, #e5f5ff);
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
    }

    .hero-subtitle {
      font-size: 0.98rem;
      color: var(--text-muted);
      max-width: 34rem;
      line-height: 1.6;
    }

    .hero-meta {
      display: flex;
      flex-wrap: wrap;
      gap: 8px;
      margin-top: 4px;
    }

    .hero-meta-badge {
      padding: 5px 10px;
      border-radius: 999px;
      border: 1px solid rgba(148, 163, 184, 0.5);
      font-size: 0.78rem;
      color: var(--text-muted);
      background: linear-gradient(
        to bottom right,
        rgba(15, 23, 42, 0.9),
        rgba(15, 23, 42, 0.7)
      );
    }

    .hero-actions {
      display: flex;
      flex-wrap: wrap;
      gap: 10px;
      margin-top: 10px;
    }

    .btn-primary,
    .btn-ghost {
      position: relative;
      display: inline-flex;
      align-items: center;
      justify-content: center;
      gap: 8px;
      padding: 10px 16px;
      border-radius: 999px;
      font-size: 0.9rem;
      font-weight: 500;
      border: 1px solid transparent;
      text-decoration: none;
      cursor: pointer;
      transition: transform var(--transition-fast), box-shadow var(--transition-fast),
        background var(--transition-fast), border-color var(--transition-fast),
        color var(--transition-fast);
    }

    .btn-primary {
      background: radial-gradient(circle at 0 0, #38bdf8, #0f172a);
      border-color: rgba(56, 189, 248, 0.8);
      box-shadow: 0 14px 34px rgba(8, 47, 73, 0.95);
      color: #0b1120;
    }

    .btn-primary span {
      color: #0b1120;
    }

    .btn-primary:hover {
      transform: translateY(-1px) scale(1.02);
      box-shadow: 0 18px 40px rgba(8, 47, 73, 1);
      background: radial-gradient(circle at 0 0, #38bdf8, #020617);
    }

    .btn-primary:active {
      transform: translateY(1px) scale(0.98);
      box-shadow: 0 8px 20px rgba(8, 47, 73, 0.9);
      background: radial-gradient(circle at 20% 0, #0ea5e9, #020617);
    }

    .btn-ghost {
      background: rgba(15, 23, 42, 0.9);
      border-color: rgba(148, 163, 184, 0.7);
      color: var(--text-muted);
    }

    .btn-ghost:hover {
      color: var(--text-main);
      background: linear-gradient(
        to bottom right,
        rgba(15, 23, 42, 0.95),
        rgba(15, 23, 42, 0.85)
      );
      border-color: rgba(148, 163, 184, 0.9);
      transform: translateY(-1px);
      box-shadow: 0 10px 22px rgba(15, 23, 42, 0.9);
    }

    .btn-ghost:active {
      transform: translateY(1px) scale(0.98);
      box-shadow: 0 6px 16px rgba(15, 23, 42, 0.95);
    }

    .btn-indicator {
      display: inline-block;
      width: 7px;
      height: 7px;
      border-radius: 999px;
      background: radial-gradient(circle at 30% 20%, #38bdf8, #22d3ee);
      box-shadow: 0 0 10px rgba(59, 130, 246, 0.9);
    }

    .hero-right {
      position: relative;
      z-index: 1;
      display: flex;
      align-items: center;
      justify-content: center;
    }

    .profile-card {
      position: relative;
      width: 100%;
      max-width: 320px;
      border-radius: var(--radius-xl);
      padding: 18px 16px 16px;
      background:
        linear-gradient(135deg, rgba(30, 64, 175, 0.8), rgba(15, 23, 42, 0.98)),
        rgba(15, 23, 42, 1);
      box-shadow: 0 22px 48px rgba(15, 23, 42, 0.95);
      border: 1px solid rgba(148, 163, 184, 0.6);
      transform-style: preserve-3d;
      transform: translateY(0) rotateX(10deg) rotateY(-8deg);
      transition: transform 260ms ease-out, box-shadow 260ms ease-out, border-color 260ms ease-out;
    }

    .profile-card:hover {
      transform: translateY(-6px) rotateX(6deg) rotateY(-4deg);
      box-shadow: 0 30px 70px rgba(15, 23, 42, 1);
      border-color: rgba(56, 189, 248, 0.7);
    }

    .profile-glow {
      position: absolute;
      inset: -20%;
      border-radius: inherit;
      background:
        radial-gradient(circle at 10% 0, rgba(56, 189, 248, 0.45), transparent 55%),
        radial-gradient(circle at 80% 100%, rgba(56, 189, 248, 0.25), transparent 60%);
      opacity: 0.4;
      filter: blur(10px);
      z-index: -1;
    }

    .profile-header {
      display: flex;
      align-items: center;
      gap: 12px;
      margin-bottom: 14px;
    }

    .profile-avatar {
      width: 52px;
      height: 52px;
      border-radius: 999px;
      border: 1px solid rgba(148, 163, 184, 0.8);
      padding: 3px;
      background:
        conic-gradient(from 210deg, rgba(56, 189, 248, 0.1), rgba(56, 189, 248, 0.8), rgba(8, 47, 73, 1), rgba(56, 189, 248, 0.1));
      display: inline-flex;
      align-items: center;
      justify-content: center;
      box-shadow: 0 10px 24px rgba(15, 23, 42, 0.9);
    }

    .profile-avatar-inner {
      width: 100%;
      height: 100%;
      border-radius: inherit;
      background: radial-gradient(circle at 30% 20%, #dbeafe, #020617 70%);
      box-shadow: inset 0 0 18px rgba(15, 23, 42, 0.95);
    }

    .profile-text-main {
      display: flex;
      flex-direction: column;
      gap: 2px;
    }

    .profile-name {
      font-size: 1.02rem;
      font-weight: 600;
    }

    .profile-role {
      font-size: 0.8rem;
      color: #cbd5f5;
    }

    .profile-location {
      font-size: 0.76rem;
      color: rgba(203, 213, 225, 0.9);
    }

    .profile-divider {
      height: 1px;
      width: 100%;
      background: linear-gradient(
        to right,
        transparent,
        rgba(148, 163, 184, 0.8),
        transparent
      );
      margin: 8px 0 10px;
    }

    .profile-highlights {
      display: flex;
      flex-direction: column;
      gap: 6px;
      margin-bottom: 10px;
    }

    .profile-pill {
      font-size: 0.76rem;
      color: #e5e7eb;
      padding: 5px 8px;
      border-radius: 999px;
      border: 1px solid rgba(148, 163, 184, 0.6);
      background: radial-gradient(circle at 0 0, rgba(56, 189, 248, 0.16), rgba(15, 23, 42, 0.9));
      display: inline-flex;
      align-items: center;
      justify-content: space-between;
      gap: 10px;
    }

    .profile-pill span {
      font-weight: 500;
      color: #e5f5ff;
    }

    .profile-footer {
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 10px;
      font-size: 0.75rem;
      color: rgba(226, 232, 240, 0.9);
    }

    .profile-status {
      display: flex;
      align-items: center;
      gap: 6px;
    }

    .status-dot {
      width: 7px;
      height: 7px;
      border-radius: 999px;
      background: radial-gradient(circle at 30% 20%, #22c55e, #16a34a);
      box-shadow: 0 0 10px rgba(34, 197, 94, 0.9);
    }

    .profile-link {
      text-decoration: none;
      color: #bae6fd;
      border-bottom: 1px dotted rgba(125, 211, 252, 0.7);
    }

    .profile-link:hover {
      color: #e0f2fe;
      border-bottom-style: solid;
    }

    /* Sections */
    .section {
      position: relative;
      border-radius: var(--radius-xl);
      padding: 22px 20px 20px;
      background: rgba(15, 23, 42, 0.94);
      border: 1px solid var(--border-subtle);
      box-shadow: 0 18px 44px rgba(15, 23, 42, 0.95);
      overflow: hidden;
    }

    .section::before {
      content: "";
      position: absolute;
      inset: 0;
      background: radial-gradient(
        circle at 10% 0%,
        rgba(56, 189, 248, 0.16),
        transparent 55%
      );
      opacity: 0;
      pointer-events: none;
      transition: opacity 260ms ease-out;
    }

    .section:hover::before {
      opacity: 1;
    }

    .section-header {
      display: flex;
      align-items: baseline;
      justify-content: space-between;
      gap: 12px;
      margin-bottom: 14px;
    }

    .section-title {
      font-size: 1rem;
      font-weight: 600;
      letter-spacing: 0.08em;
      text-transform: uppercase;
      color: #e5e7eb;
    }

    .section-subtitle {
      font-size: 0.8rem;
      color: var(--text-muted);
    }

    .section-body {
      font-size: 0.94rem;
      color: var(--text-main);
      line-height: 1.7;
    }

    .intro-grid {
      display: grid;
      grid-template-columns: minmax(0, 2.5fr) minmax(0, 1.8fr);
      gap: 20px;
      margin-top: 8px;
    }

    .intro-main p + p {
      margin-top: 10px;
    }

    .intro-list {
      margin-top: 10px;
      padding-left: 16px;
      color: var(--text-muted);
      font-size: 0.9rem;
    }

    .intro-list li + li {
      margin-top: 5px;
    }

    .profile-aside-card {
      border-radius: var(--radius-lg);
      padding: 12px 12px 11px;
      background: linear-gradient(
        145deg,
        rgba(30, 64, 175, 0.95),
        rgba(15, 23, 42, 0.98)
      );
      border: 1px solid rgba(148, 163, 184, 0.7);
      box-shadow: 0 16px 32px rgba(15, 23, 42, 0.95);
      font-size: 0.85rem;
      line-height: 1.5;
    }

    .profile-aside-card h3 {
      font-size: 0.9rem;
      margin-bottom: 6px;
      color: #e5f5ff;
    }

    .profile-aside-meta {
      display: flex;
      flex-wrap: wrap;
      gap: 6px;
      margin-top: 8px;
    }

    .profile-aside-badge {
      font-size: 0.78rem;
      padding: 4px 8px;
      border-radius: 999px;
      border: 1px solid rgba(191, 219, 254, 0.7);
      background: rgba(15, 23, 42, 0.7);
      color: #e5f5ff;
    }

    /* Contact Section */
    .contact-grid {
      display: grid;
      grid-template-columns: minmax(0, 1.6fr) minmax(0, 2.4fr);
      gap: 18px;
      margin-top: 4px;
    }

    .contact-card {
      border-radius: var(--radius-lg);
      padding: 14px 12px;
      background: linear-gradient(
        145deg,
        rgba(15, 23, 42, 0.95),
        rgba(15, 23, 42, 0.9)
      );
      border: 1px solid rgba(148, 163, 184, 0.6);
      box-shadow: 0 14px 28px rgba(15, 23, 42, 0.95);
    }

    .contact-label {
      font-size: 0.82rem;
      color: var(--text-muted);
      margin-bottom: 2px;
    }

    .contact-value {
      font-size: 0.95rem;
      font-weight: 500;
      color: #e5f5ff;
    }

    .contact-value a {
      color: inherit;
      text-decoration: none;
      border-bottom: 1px solid rgba(191, 219, 254, 0.8);
    }

    .contact-value a:hover {
      color: #ffffff;
      border-bottom-style: solid;
    }

    .contact-note {
      margin-top: 8px;
      font-size: 0.84rem;
      color: var(--text-muted);
    }

    .contact-pills {
      display: flex;
      flex-wrap: wrap;
      gap: 6px;
      margin-top: 8px;
    }

    .contact-pill {
      padding: 5px 9px;
      border-radius: 999px;
      border: 1px solid rgba(148, 163, 184, 0.7);
      font-size: 0.78rem;
      color: #cbd5f5;
      background: radial-gradient(circle at 0 0, rgba(56, 189, 248, 0.1), rgba(15, 23, 42, 0.9));
    }

    .contact-cta {
      margin-top: 8px;
      display: flex;
      flex-wrap: wrap;
      gap: 8px;
    }

    .contact-cta button {
      border: none;
      background: rgba(15, 23, 42, 0.95);
      border-radius: 999px;
      padding: 7px 12px;
      font-size: 0.82rem;
      color: var(--text-muted);
      border: 1px solid rgba(148, 163, 184, 0.7);
      cursor: pointer;
      box-shadow: 0 10px 24px rgba(15, 23, 42, 0.85);
      transition: transform var(--transition-fast), box-shadow var(--transition-fast),
        border-color var(--transition-fast), background var(--transition-fast);
    }

    .contact-cta button:hover {
      transform: translateY(-1px);
      border-color: rgba(56, 189, 248, 1);
      background: linear-gradient(
        to bottom right,
        rgba(15, 23, 42, 0.98),
        rgba(15, 23, 42, 0.9)
      );
      color: #e5f5ff;
      box-shadow: 0 16px 30px rgba(15, 23, 42, 0.95);
    }

    .contact-cta button:active {
      transform: translateY(1px) scale(0.97);
      box-shadow: 0 8px 18px rgba(15, 23, 42, 0.9);
    }

    /* Footer */
    footer {
      border-top: 1px solid rgba(30, 64, 175, 0.7);
      background: radial-gradient(circle at 50% 0, rgba(30, 64, 175, 0.5), rgba(15, 23, 42, 0.98));
      margin-top: 30px;
    }

    .footer-inner {
      max-width: 1080px;
      margin: 0 auto;
      padding: 14px 20px 16px;
      display: flex;
      flex-wrap: wrap;
      align-items: center;
      justify-content: space-between;
      gap: 10px;
      font-size: 0.78rem;
      color: rgba(148, 163, 184, 0.9);
    }

    .footer-left span {
      color: #e5e7eb;
    }

    .footer-right {
      display: flex;
      flex-wrap: wrap;
      gap: 14px;
    }

    .footer-link {
      text-decoration: none;
      color: rgba(148, 163, 184, 0.9);
      border-bottom: 1px dotted transparent;
      transition: color var(--transition-fast), border-color var(--transition-fast);
    }

    .footer-link:hover {
      color: #e5e7eb;
      border-color: rgba(148, 163, 184, 0.9);
    }

    /* Responsive */
    @media (max-width: 880px) {
      .hero {
        grid-template-columns: minmax(0, 1fr);
        padding: 22px 18px 20px;
      }

      .hero-right {
        order: -1;
      }

      .profile-card {
        max-width: 100%;
        transform: translateY(0) rotateX(0) rotateY(0);
      }

      .profile-card:hover {
        transform: translateY(-4px) rotateX(0) rotateY(0);
      }

      .hero-title {
        font-size: 1.8rem;
      }

      .intro-grid {
        grid-template-columns: minmax(0, 1fr);
      }

      .contact-grid {
        grid-template-columns: minmax(0, 1fr);
      }

      .nav {
        padding-inline: 16px;
      }

      .content {
        padding-inline: 16px;
      }
    }

    @media (max-width: 640px) {
      .nav-links {
        display: none;
      }

      .hero {
        margin-top: 8px;
      }

      .section {
        padding-inline: 16px;
      }

      .footer-inner {
        padding-inline: 16px;
      }
    }
  </style>
</head>
<body>
  <!-- Space Background -->
  <div class="space-background" aria-hidden="true">
    <div class="stars"></div>
    <div class="orb orb-1"></div>
    <div class="orb orb-2"></div>
  </div>

  <div class="page-shell">
    <!-- Header -->
    <header>
      <nav class="nav">
        <a href="#top" class="logo">
          <div class="logo-mark">
            <div class="logo-mark-inner"></div>
          </div>
          <div class="logo-text">
            <span class="logo-name">MOON HYEON JUN</span>
            <span class="logo-role">Strategic Marketer · Business Builder</span>
          </div>
        </a>

        <div class="nav-links">
          <a href="#about">About</a>
          <a href="#intro">Profile</a>
          <a href="#contact">Contact</a>
          <button class="nav-cta" onclick="document.getElementById('contact').scrollIntoView({behavior:'smooth'});">
            Contact
          </button>
        </div>
      </nav>
    </header>

    <!-- Main -->
    <main id="top">
      <div class="content">
        <!-- Hero: Name & Short Intro -->
        <section class="hero" aria-labelledby="hero-title">
          <div class="hero-orbit" aria-hidden="true"></div>
          <div class="hero-gradient-ring" aria-hidden="true"></div>

          <div class="hero-left">
            <div class="hero-tag">
              <span class="hero-tag-dot"></span>
              <span>Portfolio</span>
            </div>

            <h1 id="hero-title" class="hero-title">
              Moon Hyeon Jun
              <span>Strategic Marketer &amp; Business Builder</span>
            </h1>

            <p class="hero-subtitle">
              헬스케어, 디지털 헬스, IT를 넘나들며 비즈니스를 설계하고 성장시키는 마케터입니다.
              데이터 기반 인사이트와 스토리텔링을 결합해 브랜드와 사용자가 자연스럽게 연결되는 경험을 만드는 데 집중합니다.
            </p>

            <div class="hero-meta">
              <span class="hero-meta-badge">Marketing &amp; Growth Strategy</span>
              <span class="hero-meta-badge">Digital Healthcare &amp; BCI</span>
              <span class="hero-meta-badge">Product &amp; Service Planning</span>
            </div>

            <div class="hero-actions">
              <a href="#intro" class="btn-primary">
                <span>자기소개 바로보기</span>
              </a>
              <a href="#contact" class="btn-ghost">
                <span class="btn-indicator"></span>
                <span>협업 및 문의</span>
              </a>
            </div>
          </div>

          <div class="hero-right">
            <article class="profile-card" aria-label="Profile highlight card">
              <div class="profile-glow" aria-hidden="true"></div>
              <div class="profile-header">
                <div class="profile-avatar">
                  <div class="profile-avatar-inner"></div>
                </div>
                <div class="profile-text-main">
                  <div class="profile-name">문현준</div>
                  <div class="profile-role">Strategic Marketer · Service Planner</div>
                  <div class="profile-location">Seoul, Republic of Korea</div>
                </div>
              </div>
              <div class="profile-divider"></div>
              <div class="profile-highlights">
                <div class="profile-pill">
                  <span>8+ Years</span>
                  <span>Healthcare, Pharma, Digital Commerce, Startup</span>
                </div>
                <div class="profile-pill">
                  <span>Strengths</span>
                  데이터 기반 퍼널 분석 · 신규 서비스 런칭 · 브랜드 스토리 설계
                </div>
                <div class="profile-pill">
                  <span>Focus</span>
                  디지털 헬스케어, 뇌과학 기반 멘탈헬스 솔루션, 지속 가능한 비즈니스 모델
                </div>
              </div>
              <div class="profile-footer">
                <div class="profile-status">
                  <span class="status-dot"></span>
                  <span>새로운 도전과 협업에 열려 있습니다.</span>
                </div>
                <a class="profile-link" href="#contact">Contact</a>
              </div>
            </article>
          </div>
        </section>

        <!-- Self Introduction Section -->
        <section id="intro" class="section" aria-labelledby="intro-title">
          <div class="section-header">
            <div>
              <h2 id="intro-title" class="section-title">Self Introduction</h2>
              <p class="section-subtitle">자기소개</p>
            </div>
          </div>
          <div class="section-body intro-grid">
            <div class="intro-main">
              <p>
                저는 인문학과 법학, 그리고 경영학(MBA)을 기반으로 다양한 산업을 경험해 온 전략 마케터이자
                서비스 기획자입니다. 소비자 인사이트와 시장 구조를 읽는 눈을 바탕으로,
                <strong>“사업이 실제로 성장하는 구조”</strong>를 설계하는 데 강점을 가지고 있습니다.
              </p>
              <p>
                제 커리어의 공통점은 항상 <strong>변화의 시기</strong>에 있다는 점입니다.
                제약사의 디지털 전환, 뷰티·의료기기 커머스의 성장기, 그리고 뇌파 기반 멘탈헬스케어 스타트업까지,
                저는 새로운 시도와 실험이 필요한 시점에서 전략과 실행을 동시에 맡아 왔습니다.
              </p>
              <p>
                단순히 캠페인을 집행하는 마케터가 아니라,
                <strong>“사용자의 현실 문제를 이해하고, 그 문제를 해결하는 서비스와 비즈니스 구조를 만드는 사람”</strong>이 되고자 합니다.
                특히 중독, 정신건강, 디지털 웰빙과 같이 해결이 쉽지 않지만 반드시 다뤄야 할 문제들에 관심이 큽니다.
              </p>

              <ul class="intro-list">
                <li>데이터와 스토리, 두 언어를 모두 사용하는 마케터</li>
                <li>헬스케어·디지털 헬스·IT 영역의 도메인 이해</li>
                <li>초기 스타트업 환경에서의 제로투원(0→1) 경험과 실행력</li>
              </ul>
            </div>

            <aside class="profile-aside-card">
              <h3>제가 잘하는 일</h3>
              <p>
                서비스 아이디어를 비즈니스로 구체화하고, 숫자로 검증 가능한 형태로 구조화하는 일을 즐깁니다.
                발산과 수렴, 기획과 실행 사이를 오가며 팀을 정렬시키는 역할을 맡아 왔습니다.
              </p>
              <div class="profile-aside-meta">
                <span class="profile-aside-badge">비즈니스 모델링</span>
                <span class="profile-aside-badge">퍼널 설계 &amp; 최적화</span>
                <span class="profile-aside-badge">디지털 캠페인 전략</span>
                <span class="profile-aside-badge">시장·경쟁사 리서치</span>
              </div>
            </aside>
          </div>
        </section>

        <!-- About Section -->
        <section id="about" class="section" aria-labelledby="about-title">
          <div class="section-header">
            <div>
              <h2 id="about-title" class="section-title">About</h2>
              <p class="section-subtitle">성명 및 소개</p>
            </div>
          </div>
          <div class="section-body">
            <p>
              <strong>문현준 (Moon Hyeon Jun)</strong> · Strategic Marketer &amp; Business Builder
            </p>
            <p style="margin-top:8px;">
              법학과 MBA를 바탕으로 헬스케어, 제약, 뷰티 커머스, 디지털 헬스 스타트업 등 다양한 환경에서
              마케팅과 서비스 기획을 담당해 왔습니다. 데이터를 기반으로 한 퍼널 분석과
              시장·경쟁사 인사이트를 토대로, 매출과 사용성 개선을 동시에 추구하는 전략 수립에 익숙합니다.
            </p>
            <p style="margin-top:8px;">
              현재는 뇌파 기반 멘탈헬스케어 솔루션과 중독 완화 서비스를 탐구하며,
              기술과 사람 사이의 간극을 줄이는 실용적인 디지털 헬스 서비스를 만드는 것을 목표로 하고 있습니다.
            </p>
          </div>
        </section>

        <!-- Contact Section -->
        <section id="contact" class="section" aria-labelledby="contact-title">
          <div class="section-header">
            <div>
              <h2 id="contact-title" class="section-title">Contact</h2>
              <p class="section-subtitle">연락처</p>
            </div>
          </div>
          <div class="section-body contact-grid">
            <div class="contact-card">
              <div class="contact-label">Email</div>
              <div class="contact-value">
                <!-- 필요에 맞게 이메일 주소 수정 -->
                <a href="mailto:your.email@example.com">your.email@example.com</a>
              </div>

              <div class="contact-label" style="margin-top:10px;">LinkedIn</div>
              <div class="contact-value">
                <!-- 실제 링크로 교체 -->
                <a href="https://www.linkedin.com" target="_blank" rel="noopener noreferrer">
                  linkedin.com/in/your-profile
                </a>
              </div>

              <div class="contact-label" style="margin-top:10px;">Location</div>
              <div class="contact-value">Seoul, Republic of Korea</div>

              <p class="contact-note">
                프로젝트 제안, 채용 관련 문의, 협업 논의 등 언제든 편하게 연락 주시면
                업무 맥락과 목표를 먼저 이해하고 성실하게 답변드리겠습니다.
              </p>
            </div>

            <div class="contact-card">
              <div class="contact-label">Preferred Topics</div>
              <div class="contact-pills">
                <span class="contact-pill">디지털 헬스케어 서비스 기획</span>
                <span class="contact-pill">헬스케어·제약 분야 마케팅</span>
                <span class="contact-pill">멘탈헬스·중독 관련 디지털 솔루션</span>
                <span class="contact-pill">스타트업 초기 전략 및 그로스</span>
              </div>

              <div class="contact-cta">
                <button type="button" onclick="window.location.href='mailto:your.email@example.com';">
                  메일 보내기
                </button>
                <button type="button" onclick="document.getElementById('top').scrollIntoView({behavior:'smooth'});">
                  상단으로 이동
                </button>
              </div>
            </div>
          </div>
        </section>
      </div>
    </main>

    <!-- Footer -->
    <footer>
      <div class="footer-inner">
        <div class="footer-left">
          <span>&copy; <span id="year"></span> Moon Hyeon Jun.</span>
          <span> All rights reserved.</span>
        </div>
        <div class="footer-right">
          <a href="#top" class="footer-link">Back to top</a>
          <a href="#contact" class="footer-link">Contact</a>
        </div>
      </div>
    </footer>
  </div>

  <script>
    // 동적 저작권 연도 표시
    (function () {
      var yearSpan = document.getElementById("year");
      if (yearSpan) {
        yearSpan.textContent = new Date().getFullYear();
      }
    })();
  </script>
</body>
</html>
