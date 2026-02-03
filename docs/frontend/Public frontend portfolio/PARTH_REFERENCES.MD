
# DETAILS OF PARTH REFERENCES - 
website url -  https://parthh.in/      
<!-- visit upper url for references -->

```JSON
{
  "designSystem": {
    "meta": {
      "name": "Parthh Web Design System",
      "brandEssence": "Emerald, precise, engineering-driven personal brand for a full‑stack dev & founder.",
      "targetUse": "Parthh.in marketing site, portfolio, blog, and future product landing pages.",
      "tone": [
        "Technical yet friendly",
        "High‑contrast and legible",
        "Confident and minimal",
        "Motion‑enhanced but not flashy"
      ],
      "grid": {
        "pageWidth": {
          "maxWidth": 1200,
          "unit": "px",
          "rationale": "Keeps content readable on large screens while feeling focused and premium [page:1]."
        },
        "columns": {
          "desktop": 12,
          "tablet": 8,
          "mobile": 4,
          "gutter": 24,
          "unit": "px",
          "rationale": "Allows flexible hero layouts, cards, and two‑column content blocks used across the homepage [page:1]."
        },
        "breakpoints": {
          "xs": {
            "min": 0,
            "max": 479,
            "description": "Small mobile"
          },
          "sm": {
            "min": 480,
            "max": 767,
            "description": "Mobile / phablet"
          },
          "md": {
            "min": 768,
            "max": 1023,
            "description": "Tablet / small laptop"
          },
          "lg": {
            "min": 1024,
            "max": 1439,
            "description": "Desktop"
          },
          "xl": {
            "min": 1440,
            "max": 9999,
            "description": "Large desktop"
          }
        }
      }
    },
    "colors": {
      "palette": {
        "primary": {
          "name": "Emerald",
          "rationale": "The brand already leans into an emerald/green identity (\"Emerald Creative Engineer\"), so primary is a clean emerald that reads well on dark and light sections [page:1].",
          "scale": {
            "50": "#ECFDF5",
            "100": "#D1FAE5",
            "200": "#A7F3D0",
            "300": "#6EE7B7",
            "400": "#34D399",
            "500": "#10B981",
            "600": "#059669",
            "700": "#047857",
            "800": "#065F46",
            "900": "#064E3B"
          },
          "usage": {
            "500": "Primary CTAs, key badges, skill tags on light backgrounds.",
            "600": "Hover state for primary CTAs on light backgrounds.",
            "700": "Primary CTA background on dark sections.",
            "100_200": "Subtle fills for cards, timelines, or micro‑interaction backgrounds."
          }
        },
        "secondary": {
          "name": "Electric Indigo",
          "rationale": "Supports the tech/futuristic impression in sections like Rune and skills without competing with the primary emerald [page:1].",
          "scale": {
            "50": "#EEF2FF",
            "100": "#E0E7FF",
            "200": "#C7D2FE",
            "300": "#A5B4FC",
            "400": "#818CF8",
            "500": "#6366F1",
            "600": "#4F46E5",
            "700": "#4338CA",
            "800": "#3730A3",
            "900": "#312E81"
          },
          "usage": {
            "500": "Secondary CTAs (e.g., 'See more projects', external links).",
            "400": "Accent underlines, focus outlines on dark sections.",
            "50_100": "Background chips behind tech stack, tags."
          }
        },
        "accent": {
          "name": "Warm Amber",
          "rationale": "Micro‑highlights for time, status (\"Available for work\"), or motion hints, adding warmth and human touch [page:1].",
          "scale": {
            "50": "#FFFBEB",
            "100": "#FEF3C7",
            "200": "#FDE68A",
            "300": "#FCD34D",
            "400": "#FBBF24",
            "500": "#F59E0B",
            "600": "#D97706",
            "700": "#B45309",
            "800": "#92400E",
            "900": "#78350F"
          },
          "usage": {
            "400": "Badges like 'Available globally', 'Latest push', or subtle highlights.",
            "500": "Icons, tiny details in micro‑interactions, e.g., music playing dot.",
            "100_200": "Soft background for status pills."
          }
        },
        "neutral": {
          "name": "Slate",
          "mode": "Dark‑leaning neutral system that works for both light and dark sections.",
          "scale": {
            "0": "#FFFFFF",
            "25": "#F9FAFB",
            "50": "#F3F4F6",
            "100": "#E5E7EB",
            "200": "#D1D5DB",
            "300": "#9CA3AF",
            "400": "#6B7280",
            "500": "#4B5563",
            "600": "#374151",
            "700": "#111827",
            "800": "#020617",
            "900": "#02040C"
          },
          "usage": {
            "bg_body": "neutral.900",
            "bg_alt": "neutral.800",
            "bg_card": "neutral.800 on dark sections, neutral.0 on light sections.",
            "border_subtle": "neutral.800 (dark mode) or neutral.100 (light mode).",
            "text_primary_on_dark": "neutral.0",
            "text_secondary_on_dark": "neutral.300",
            "text_muted_on_dark": "neutral.400",
            "text_primary_on_light": "neutral.900",
            "text_secondary_on_light": "neutral.600"
          }
        },
        "semantic": {
          "success": {
            "base": "#22C55E",
            "on": "#022C22",
            "usage": "Form success messages, 'Message sent', 'Available' status tags."
          },
          "info": {
            "base": "#0EA5E9",
            "on": "#011627",
            "usage": "Informational banners, tooltips, 'Remote' labels."
          },
          "warning": {
            "base": "#F97316",
            "on": "#1F1306",
            "usage": "Soft warnings like 'Experimental feature', 'Beta'."
          },
          "error": {
            "base": "#EF4444",
            "on": "#2F0B0B",
            "usage": "Form errors, validation states for inputs."
          },
          "focusRing": {
            "base": "#22C55E",
            "usage": "Unified focus outline color on interactive components for accessibility."
          }
        }
      },
      "elevation": {
        "shadowSm": "0 1px 2px rgba(15, 23, 42, 0.25)",
        "shadowMd": "0 4px 10px rgba(15, 23, 42, 0.35)",
        "shadowLg": "0 18px 45px rgba(15, 23, 42, 0.45)",
        "rationale": "Depth is reserved for cards like testimonials, projects and primary CTAs, echoing the 'interfaces you can feel' tagline [page:1]."
      }
    },
    "typography": {
      "fonts": {
        "brand": {
          "name": "Space Grotesk",
          "fallback": "system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif",
          "usage": "Large headings, hero wordmarks like 'PARTH' and 'Interfaces you can feel' to feel modern, geometric, and engineering‑forward."
        },
        "body": {
          "name": "Inter",
          "fallback": "system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif",
          "usage": "Body copy, long paragraphs (about, testimonials, philosophy) for optimal legibility and consistent metrics."
        },
        "mono": {
          "name": "JetBrains Mono",
          "fallback": "SFMono-Regular, Menlo, Monaco, Consolas, 'Liberation Mono', 'Courier New', monospace",
          "usage": "Code snippets, command labels like 'Open Command Menu', timestamps, Git last push section [page:1]."
        }
      },
      "scale": {
        "baseFontSize": 16,
        "ratio": 1.2,
        "rationale": "A minor third scale provides enough contrast between levels while preserving smooth hierarchy on both mobile and desktop.",
        "sizesPx": {
          "xs": 12,
          "sm": 14,
          "md": 16,
          "lg": 18,
          "xl": 20,
          "h6": 16,
          "h5": 18,
          "h4": 24,
          "h3": 30,
          "h2": 36,
          "h1": 44,
          "display": 60
        },
        "lineHeights": {
          "tight": 1.1,
          "snug": 1.2,
          "normal": 1.5,
          "relaxed": 1.7
        }
      },
      "styles": {
        "display": {
          "fontFamily": "Space Grotesk",
          "fontSize": 60,
          "lineHeight": 1.05,
          "letterSpacing": -0.03,
          "fontWeight": 700,
          "usage": "Main hero phrases like 'I DESIGN AND BUILD PRODUCTS THAT deliver real impact.' on desktop [page:1]."
        },
        "h1": {
          "fontFamily": "Space Grotesk",
          "fontSize": 44,
          "lineHeight": 1.1,
          "letterSpacing": -0.02,
          "fontWeight": 700,
          "usage": "Major section titles such as 'Interfaces you can feel', 'The Magic Behind', 'The Voices Behind' [page:1]."
        },
        "h2": {
          "fontFamily": "Space Grotesk",
          "fontSize": 36,
          "lineHeight": 1.15,
          "letterSpacing": -0.02,
          "fontWeight": 600,
          "usage": "Sub‑section headings, e.g., 'Available globally', 'Let's build something that actually works', 'Founder of Rune' [page:1]."
        },
        "h3": {
          "fontFamily": "Space Grotesk",
          "fontSize": 30,
          "lineHeight": 1.2,
          "letterSpacing": -0.01,
          "fontWeight": 600,
          "usage": "Card titles like project names, testimonial names in compact layouts."
        },
        "h4": {
          "fontFamily": "Space Grotesk",
          "fontSize": 24,
          "lineHeight": 1.2,
          "letterSpacing": -0.005,
          "fontWeight": 600,
          "usage": "Supporting section headings, side labels (e.g., 'Last Played', 'Quick Glance')."
        },
        "subtitle": {
          "fontFamily": "Inter",
          "fontSize": 18,
          "lineHeight": 1.4,
          "fontWeight": 500,
          "usage": "Short intro text under headings and hero supporting descriptions."
        },
        "body": {
          "regular": {
            "fontFamily": "Inter",
            "fontSize": 16,
            "lineHeight": 1.6,
            "fontWeight": 400,
            "usage": "Paragraphs about Parth, project descriptions, blog intros [page:1]."
          },
          "muted": {
            "fontFamily": "Inter",
            "fontSize": 14,
            "lineHeight": 1.6,
            "fontWeight": 400,
            "usage": "Metadata such as role labels, timestamps, locations, legal text."
          }
        },
        "label": {
          "sm": {
            "fontFamily": "Inter",
            "fontSize": 12,
            "lineHeight": 1.4,
            "fontWeight": 500,
            "letterSpacing": 0.06,
            "textTransform": "uppercase",
            "usage": "Eyebrow labels like 'VENTURE', 'SHOWCASE', 'MY SKILLSET', or taglines above headings [page:1]."
          },
          "md": {
            "fontFamily": "Inter",
            "fontSize": 13,
            "lineHeight": 1.4,
            "fontWeight": 600,
            "letterSpacing": 0.08,
            "textTransform": "uppercase",
            "usage": "Button labels, nav, chips."
          }
        },
        "button": {
          "fontFamily": "Inter",
          "fontSize": 14,
          "lineHeight": 1.4,
          "fontWeight": 600,
          "letterSpacing": 0.04,
          "textTransform": "none",
          "usage": "All CTAs like 'Book a Call', 'Connect now', 'See more projects' [page:1]."
        },
        "code": {
          "fontFamily": "JetBrains Mono",
          "fontSize": 13,
          "lineHeight": 1.5,
          "fontWeight": 400,
          "usage": "Inline code, Git excerpts, potential blog snippets."
        }
      },
      "responsiveRules": {
        "xs_sm": {
          "displayToH1": "display shrinks to 44px, h1 to 36px, h2 to 28px for comfortable reading.",
          "paragraphWidth": "Max 36rem where possible to avoid overly long lines.",
          "centerAlignHero": "On small screens hero text becomes center‑aligned with stacked actions."
        }
      }
    },
    "spacing": {
      "scale": {
        "0": 0,
        "1": 4,
        "2": 8,
        "3": 12,
        "4": 16,
        "5": 20,
        "6": 24,
        "7": 32,
        "8": 40,
        "9": 48,
        "10": 64,
        "11": 80,
        "12": 96
      },
      "usage": {
        "sectionY": {
          "mobile": 40,
          "desktop": 80,
          "rationale": "Matches generous breathing room seen in hero and testimonials to maintain a premium feel [page:1]."
        },
        "stackedElements": {
          "headingToSubtitle": 8,
          "subtitleToBody": 12,
          "bodyToPrimaryAction": 20,
          "rationale": "Keeps clear visual hierarchy and scannability, especially in hero and 'Quick Glance' content [page:1]."
        },
        "cardPadding": {
          "sm": 16,
          "md": 20,
          "lg": 24,
          "rationale": "Consistent tap area and card interior spacing for testimonials, project tiles, and skill chips."
        },
        "gridGap": {
          "row": 24,
          "column": 24,
          "rationale": "Aligns with 24px gutter for consistent rhythm."
        }
      }
    },
    "layout": {
      "patterns": {
        "page": {
          "background": "neutral.900 with alternating neutral.800 bands for major sections.",
          "maxWidth": 1200,
          "centered": true,
          "paddingX": {
            "xs": 16,
            "sm": 20,
            "md": 24,
            "lg": 32,
            "xl": 0
          }
        },
        "hero": {
          "structure": "Two‑column on md+ (text left, visual/abstract element right), single column on mobile.",
          "alignment": "Left‑aligned typography; primary CTA row near the fold.",
          "elements": [
            "Eyebrow label indicating role (e.g., 'CREATIVE ENGINEER')",
            "Display heading and supporting body",
            "Location and time row using subtle accent",
            "CTA group: primary 'Book a Call', secondary 'View work' or 'Download resume'"
          ],
          "rationale": "Reflects existing hero structure but tightens hierarchy and CTA clarity [page:1]."
        },
        "twoColumn": {
          "pattern": "For sections like 'The Magic Behind' and 'A Quick Glance', use text column + supporting visuals/testimonials.",
          "stackOn": "sm",
          "columnWidthDesktop": "6 / 12 each"
        },
        "cardsGrid": {
          "pattern": "Responsive grid of project cards, testimonials, skill clusters.",
          "columns": {
            "xs": 1,
            "sm": 2,
            "lg": 3
          },
          "gap": 24
        }
      }
    },
    "components": {
      "button": {
        "variants": {
          "primary": {
            "default": {
              "backgroundColor": "primary.500",
              "textColor": "neutral.0",
              "borderColor": "transparent",
              "borderRadius": 999,
              "paddingX": 20,
              "paddingY": 10,
              "gap": 8,
              "shadow": "shadowMd"
            },
            "hover": {
              "backgroundColor": "primary.600",
              "shadow": "shadowLg",
              "transform": "translateY(-1px)",
              "transition": "all 160ms ease-out"
            },
            "active": {
              "backgroundColor": "primary.700",
              "shadow": "shadowSm",
              "transform": "translateY(0)"
            },
            "disabled": {
              "backgroundColor": "neutral.700",
              "textColor": "neutral.400",
              "shadow": "none",
              "cursor": "not-allowed",
              "opacity": 0.6
            },
            "focusVisible": {
              "outline": "2px solid semantic.focusRing.base",
              "outlineOffset": 3
            },
            "usage": "High‑intent actions like 'Book a Call', 'Connect now', 'Available for work'."
          },
          "secondary": {
            "default": {
              "backgroundColor": "transparent",
              "textColor": "neutral.0",
              "borderColor": "neutral.600",
              "borderRadius": 999,
              "paddingX": 18,
              "paddingY": 9,
              "shadow": "none"
            },
            "hover": {
              "backgroundColor": "neutral.800",
              "borderColor": "neutral.400"
            },
            "active": {
              "backgroundColor": "neutral.800",
              "borderColor": "neutral.500"
            },
            "focusVisible": {
              "outline": "2px solid semantic.focusRing.base",
              "outlineOffset": 3
            },
            "usage": "Lower‑priority actions: 'See more projects', 'Dive in deeper', view social links."
          },
          "ghost": {
            "default": {
              "backgroundColor": "transparent",
              "textColor": "neutral.300",
              "borderColor": "transparent",
              "paddingX": 12,
              "paddingY": 8,
              "borderRadius": 999
            },
            "hover": {
              "backgroundColor": "neutral.800",
              "textColor": "neutral.0"
            },
            "usage": "Inline text actions, 'Tap to copy email', 'Open command menu'."
          },
          "chip": {
            "default": {
              "backgroundColor": "neutral.800",
              "textColor": "neutral.200",
              "borderColor": "neutral.700",
              "borderRadius": 999,
              "paddingX": 12,
              "paddingY": 6
            },
            "selected": {
              "backgroundColor": "primary.900",
              "borderColor": "primary.500",
              "textColor": "primary.100"
            },
            "usage": "Skill tags, filters for projects, location/time badges."
          }
        }
      },
      "link": {
        "default": {
          "textColor": "secondary.400",
          "textDecoration": "none",
          "fontWeight": 500
        },
        "hover": {
          "textColor": "secondary.300",
          "textDecoration": "underline",
          "decorationThickness": "from-font"
        },
        "focusVisible": {
          "outline": "2px solid semantic.focusRing.base",
          "outlineOffset": 2
        },
        "visited": {
          "textColor": "secondary.500"
        },
        "usageNotes": "Inline links in paragraphs and card footers must always show clear hover/focus to support discoverability and accessibility."
      },
      "nav": {
        "desktop": {
          "height": 64,
          "background": "rgba(2,6,23,0.92)",
          "backdropFilter": "blur(16px)",
          "borderBottom": "1px solid rgba(15,23,42,0.6)",
          "brandLockup": {
            "logoSize": 24,
            "wordmarkFont": "Space Grotesk",
            "wordmarkWeight": 600,
            "wordmarkSize": 18
          },
          "item": {
            "fontStyle": "label.md",
            "textColor": "neutral.300",
            "paddingX": 14,
            "paddingY": 10,
            "borderRadius": 999,
            "hover": {
              "backgroundColor": "neutral.800",
              "textColor": "neutral.0"
            },
            "active": {
              "backgroundColor": "primary.900",
              "textColor": "primary.200"
            }
          },
          "cta": {
            "component": "button.primary",
            "label": "Book a Call"
          }
        },
        "mobile": {
          "height": 56,
          "background": "neutral.900",
          "burger": {
            "size": 20,
            "strokeWidth": 1.5,
            "hitArea": 40
          },
          "overlay": {
            "background": "rgba(2,6,23,0.98)",
            "itemSpacing": 16
          }
        }
      },
      "card": {
        "base": {
          "backgroundColor": "neutral.800",
          "borderRadius": 20,
          "borderColor": "rgba(148,163,184,0.16)",
          "borderWidth": 1,
          "padding": 20,
          "shadow": "shadowSm"
        },
        "hoverable": {
          "transform": "translateY(-4px)",
          "shadow": "shadowMd",
          "transition": "all 180ms ease-out"
        },
        "testimonials": {
          "header": {
            "layout": "avatar + name + role stacked",
            "spacingY": 8
          },
          "quote": {
            "fontStyle": "body.regular",
            "textColor": "neutral.100"
          },
          "decoration": {
            "accentBar": "2px solid primary.500 at the top"
          },
          "usage": "Testimonial grid with consistent height and scroll if carousel is used, aligning with the 'Voices Behind' section [page:1]."
        },
        "project": {
          "thumbnailRatio": "16:9",
          "badgeRowSpacing": 8,
          "titleStyle": "h4",
          "stackRowSpacing": 4,
          "usage": "Portfolio template and Rune projects with logos/stack tags [page:1]."
        }
      },
      "tag": {
        "eyebrow": {
          "backgroundColor": "rgba(15,118,110,0.18)",
          "textColor": "primary.200",
          "borderRadius": 999,
          "paddingX": 10,
          "paddingY": 4,
          "fontStyle": "label.sm",
          "usage": "Section labels above headings: 'VENTURE', 'SHOWCASE', 'MY SKILLSET'."
        },
        "status": {
          "available": {
            "backgroundColor": "rgba(34,197,94,0.15)",
            "textColor": "success.base",
            "icon": "dot",
            "iconSize": 6
          },
          "busy": {
            "backgroundColor": "rgba(251,191,36,0.12)",
            "textColor": "warning.base"
          }
        },
        "pill": {
          "backgroundColor": "neutral.800",
          "borderRadius": 999,
          "paddingX": 10,
          "paddingY": 4,
          "textColor": "neutral.200",
          "fontSize": 12,
          "usage": "Location, timezone badges ('Noida, IN', 'Available globally') [page:1]."
        }
      },
      "input": {
        "textField": {
          "backgroundColor": "neutral.900",
          "borderColor": "neutral.700",
          "borderRadius": 999,
          "paddingX": 16,
          "paddingY": 10,
          "fontStyle": "body.regular",
          "placeholderColor": "neutral.500",
          "hover": {
            "borderColor": "neutral.500"
          },
          "focusVisible": {
            "borderColor": "primary.500",
            "outline": "2px solid rgba(16,185,129,0.4)",
            "outlineOffset": 0
          },
          "error": {
            "borderColor": "semantic.error.base",
            "helperTextColor": "semantic.error.base"
          },
          "usage": "Contact form, guestbook signatures, email fields [page:1]."
        },
        "textarea": {
          "borderRadius": 16,
          "paddingX": 16,
          "paddingY": 12,
          "minHeight": 120,
          "resize": "vertical"
        },
        "toggle": {
          "track": {
            "width": 40,
            "height": 22,
            "backgroundOff": "neutral.700",
            "backgroundOn": "primary.500",
            "borderRadius": 999
          },
          "thumb": {
            "size": 18,
            "background": "neutral.0",
            "shadow": "shadowSm"
          }
        }
      },
      "chipList": {
        "layout": "wrap",
        "gap": 8,
        "usage": "Skillset section where logos and labels need to be scannable yet dense [page:1]."
      },
      "avatar": {
        "sizes": {
          "sm": 32,
          "md": 48,
          "lg": 72
        },
        "shape": "circle",
        "border": "2px solid neutral.800",
        "statusDot": {
          "size": 10,
          "position": "bottom-right",
          "onlineColor": "success.base",
          "offlineColor": "neutral.600"
        },
        "usage": "Parth avatar in footer and about block, testimonial authors, visitors in guestbook [page:1]."
      },
      "timeline": {
        "orientation": "horizontal for 'Adaptable across time zones', vertical for experience in about page.",
        "dot": {
          "size": 10,
          "color": "accent.400"
        },
        "line": {
          "color": "neutral.700",
          "width": 1
        }
      },
      "musicNowPlaying": {
        "layout": "card.base with media thumbnail left, text block right.",
        "accent": {
          "progressBarColor": "accent.400",
          "playingDotColor": "accent.500"
        },
        "typography": {
          "track": "body.regular",
          "artist": "body.muted"
        },
        "usage": "Last Played 'Rakhlo Tum Chupaake' module [page:1]."
      }
    },
    "states": {
      "interaction": {
        "hover": {
          "duration": 160,
          "easing": "cubic-bezier(0.21,0.53,0.29,0.99)",
          "usage": "Buttons, cards, links, skill chips."
        },
        "focusVisible": {
          "outlineStyle": "2px solid semantic.focusRing.base",
          "outlineOffset": 3,
          "rationale": "Keyboard users can clearly see focus, passing WCAG 2.1 guidelines."
        },
        "active": {
          "scale": 0.98,
          "usage": "Click/tap feedback for primary interactive components."
        }
      },
      "motion": {
        "global": {
          "defaultDuration": 220,
          "defaultEasing": "cubic-bezier(0.2,0.8,0.2,1)",
          "reducedMotion": "Honor prefers-reduced-motion by disabling non‑essential transitions and replacing with opacity/position changes only."
        },
        "micro": {
          "hoverLift": "TranslateY(-2px) on hover for cards.",
          "iconTilt": "Subtle 2–3deg rotation and scale for icons when hovered, especially in skillset area.",
          "emailCopy": "Tap to copy triggers brief scale + color flash on pill and a toast confirmation."
        },
        "pageTransitions": {
          "type": "fade-slide",
          "from": {
            "opacity": 0,
            "translateY": 8
          },
          "to": {
            "opacity": 1,
            "translateY": 0
          },
          "duration": 260
        }
      }
    },
    "accessibility": {
      "colorContrast": {
        "minRatioBodyText": 4.5,
        "minRatioLargeText": 3,
        "notes": "Primary 500 on neutral.900, neutral.0 on neutral.800, and secondary 400 on dark backgrounds must all meet WCAG AA contrast."
      },
      "focusOrder": {
        "rules": [
          "Logical top‑to‑bottom and left‑to‑right focus order.",
          "Skip links for 'Skip to main content' at the start.",
          "Command menu trigger accessible via keyboard shortcut (e.g., ⌘K / Ctrl+K) and visible button."
        ]
      },
      "touchTargets": {
        "minSize": 44,
        "unit": "px",
        "rationale": "Buttons, chips and nav items should be at least 44x44px to ensure comfortable tapping."
      },
      "aria": {
        "usage": {
          "carousel": "Testimonials use aria-roledescription='carousel' with next/prev buttons labelled.",
          "iconOnlyButtons": "Always provide aria-label (e.g., 'Open LinkedIn profile', 'Copy email').",
          "musicCard": "Use aria-label like 'Last played track: Rakhlo Tum Chupaake by Arpit Bala' [page:1]."
        }
      }
    },
    "tokensTree": {
      "colors": {
        "primary": "colors.palette.primary",
        "secondary": "colors.palette.secondary",
        "accent": "colors.palette.accent",
        "neutral": "colors.palette.neutral",
        "semantic": "colors.palette.semantic"
      },
      "typography": {
        "display": "typography.styles.display",
        "h1": "typography.styles.h1",
        "h2": "typography.styles.h2",
        "h3": "typography.styles.h3",
        "h4": "typography.styles.h4",
        "subtitle": "typography.styles.subtitle",
        "body": "typography.styles.body",
        "label": "typography.styles.label",
        "button": "typography.styles.button",
        "code": "typography.styles.code"
      },
      "spacing": "spacing.scale",
      "components": {
        "button": "components.button",
        "link": "components.link",
        "nav": "components.nav",
        "card": "components.card",
        "tag": "components.tag",
        "input": "components.input",
        "chipList": "components.chipList",
        "avatar": "components.avatar",
        "timeline": "components.timeline",
        "musicNowPlaying": "components.musicNowPlaying"
      }
    }
  }
}
```