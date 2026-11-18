```typescript
interface Hacker {
  break(target: Scope): Report
}

interface Developer {
  build(idea: Idea): Production
}

class Muhammed implements Hacker, Developer {
  readonly speaks = ["Arabic", "English"]

  get whoami(): { now: string[]; past: string[] } {
    return {
      now: ["full-stack developer", "security researcher", "building Flint (flint.ps)"],
      past: ["Trusted Security Researcher @ Meta — web, Android & iOS"],
    }
  }

  get coding(): Record<"expert" | "advanced" | "focus" | "offense", string[]> {
    return {
      expert: ["Laravel", "Vue"],
      advanced: ["Go", "Rust", "TypeScript", "JavaScript", "React", "Node", "PHP", "Python", "Tailwind"],
      focus: ["application security", "reverse engineering", "full-stack web"],
      offense: ["Burp Suite", "Frida", "jadx", "mitmproxy"],
    }
  }

  break(target: Scope): Report {
    if (!target.authorized) throw new Error("consent first, always")
    return this.recon(target).exploit().writeup({ repro: true })
  }

  build(idea: Idea): Production {
    return this.design(idea).ship()
  }

  get contact(): Record<string, string> {
    return {
      email: "hi@mumd.dev",
      github: "iMumd",
    }
  }
}

export default new Muhammed()
```
