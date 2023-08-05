
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
 
      , u = {}
      , l = u.toString
      , c = u.hasOwnProperty
      , f = {}
      , d = function(e, t) {
        return new d.fn.init(e,t)
    }
      , p = /^[\s\uFEFF\xA0]+|[\s\uFEFF\xA0]+$/g
      , h = /^-ms-/
      , g = /-([\da-z])/gi
      , m = function(e, t) {
        return t.toUpperCase()
    };
    function v(e) {
        var t = !!e && "length"in e && e.length
          , n = d.type(e);
        return "function" !== n && !d.isWindow(e) && ("array" === n || 0 === t || "number" == typeof t && t > 0 && t - 1 in e)
    }
    d.fn = d.prototype = {
        jquery: "1.12.4",
        constructor: d,
        selector: "",
        length: 0,
        toArray: function() {
            return i.call(this)
        },
        get: function(e) {
            return null != e ? e < 0 ? this[e + this.length] : this[e] : i.call(this)
        },
        pushStack: function(e) {
            var t = d.merge(this.constructor(), e);
            return t.prevObject = this,
            t.context = this.context,
            t
        },
        each: function(e) {
            return d.each(this, e)
        },
        map: function(e) {
            return this.pushStack(d.map(this, function(t, n) {
                return e.call(t, n, t)
            }))
        },
        slice: function() {
            return this.pushStack(i.apply(this, arguments))
        },
        first: function() {
            return this.eq(0)
        },
        last: function() {
            return this.eq(-1)
        },
        eq: function(e) {
            var t = this.length
              , n = +e + (e < 0 ? t : 0);
            return this.pushStack(n >= 0 && n < t ? [this[n]] : [])
        },
        end: function() {
            return this.prevObject || this.constructor()
        },
        push: a,
        sort: n.sort,
        splice: n.splice
    },
    d.extend = d.fn.extend = function() {
        var e, t, n, r, i, o, a = arguments[0] || {}, s = 1, u = arguments.length, l = !1;
        for ("boolean" == typeof a && (l = a,
        a = arguments[s] || {},
        s++),
        "object" == typeof a || d.isFunction(a) || (a = {}),
        s === u && (a = this,
        s--); s < u; s++)
            if (null != (i = arguments[s]))
                for (r in i)
                    e = a[r],
                    n = i[r],
                    "__proto__" !== r && a !== n && (l && n && (d.isPlainObject(n) || (t = d.isArray(n))) ? (t ? (t = !1,
                    o = e && d.isArray(e) ? e : []) : o = e && d.isPlainObject(e) ? e : {},
                    a[r] = d.extend(l, o, n)) : void 0 !== n && (a[r] = n));
        return a
    }
    ,
    d.extend({
        expando: "jQuery" + ("1.12.4" + Math.random()).replace(/\D/g, ""),
        isReady: !0,
        error: function(e) {
            throw new Error(e)
        },
        noop: function() {},
        isFunction: function(e) {
            return "function" === d.type(e)
        },
        isArray: Array.isArray || function(e) {
            return "array" === d.type(e)
        }
        ,
        isWindow: function(e) {
            return null != e && e == e.window
        },
        isNumeric: function(e) {
            var t = e && e.toString();
            return !d.isArray(e) && t - parseFloat(t) + 1 >= 0
        },
        isEmptyObject: function(e) {
            var t;
            for (t in e)
                return !1;
            return !0
        },
        isPlainObject: function(e) {
            var t;
            if (!e || "object" !== d.type(e) || e.nodeType || d.isWindow(e))
                return !1;
            try {
                if (e.constructor && !c.call(e, "constructor") && !c.call(e.constructor.prototype, "isPrototypeOf"))
                    return !1
            } catch (e) {
                return !1
            }
            if (!f.ownFirst)
                for (t in e)
                    return c.call(e, t);
            for (t in e)
                ;
            return void 0 === t || c.call(e, t)
        },
        type: function(e) {
            return null == e ? e + "" : "object" == typeof e || "function" == typeof e ? u[l.call(e)] || "object" : typeof e
        },
        globalEval: function(t) {
            t && d.trim(t) && (e.execScript || function(t) {
                e.eval.call(e, t)
            }
            )(t)
        },
        camelCase: function(e) {
            return e.replace(h, "ms-").replace(g, m)
        },
        nodeName: function(e, t) {
            return e.nodeName && e.nodeName.toLowerCase() === t.toLowerCase()
        },
        each: function(e, t) {
            var n, r = 0;
            if (v(e))
                for (n = e.length; r < n && !1 !== t.call(e[r], r, e[r]); r++)
                    ;
            else
                for (r in e)
                    if (!1 === t.call(e[r], r, e[r]))
                        break;
            return e
        },
        trim: function(e) {
            return null == e ? "" : (e + "").replace(p, "")
        },
        makeArray: function(e, t) {
            var n = t || [];
            return null != e && (v(Object(e)) ? d.merge(n, "string" == typeof e ? [e] : e) : a.call(n, e)),
            n
        },
        inArray: function(e, t, n) {
            var r;
            if (t) {
                if (s)
                    return s.call(t, e, n);
                for (r = t.length,
                n = n ? n < 0 ? Math.max(0, r + n) : n : 0; n < r; n++)
                    if (n in t && t[n] === e)
                        return n
            }
            return -1
        },
        merge: function(e, t) {
            for (var n = +t.length, r = 0, i = e.length; r < n; )
                e[i++] = t[r++];
            if (n != n)
                for (; void 0 !== t[r]; )
                    e[i++] = t[r++];
            return e.length = i,
            e
        },
        grep: function(e, t, n) {
            for (var r = [], i = 0, o = e.length, a = !n; i < o; i++)
                !t(e[i], i) !== a && r.push(e[i]);
            return r
        },
        map: function(e, t, n) {
            var r, i, a = 0, s = [];
            if (v(e))
                for (r = e.length; a < r; a++)
                    null != (i = t(e[a], a, n)) && s.push(i);
            else
                for (a in e)
                    null != (i = t(e[a], a, n)) && s.push(i);
            return o.apply([], s)
        },
        guid: 1,
        proxy: function(e, t) {
            var n, r, o;
            if ("string" == typeof t && (o = e[t],
            t = e,
            e = o),
            d.isFunction(e))
                return n = i.call(arguments, 2),
                (r = function() {
                    return e.apply(t || this, n.concat(i.call(arguments)))
                }
                ).guid = e.guid = e.guid || d.guid++,
                r
        },
        now: function() {
            return +new Date
        },
        support: f
    }),
    "function" == typeof Symbol && (d.fn[Symbol.iterator] = n[Symbol.iterator]),
    d.each("Boolean Number String Function Array Date RegExp Object Error Symbol".split(" "), function(e, t) {
        u["[object " + t + "]"] = t.toLowerCase()
    });
    var y = function(e) {
        var t, n, r, i, o, a, s, u, l, c, f, d, p, h, g, m, v, y, x, b = "sizzle" + 1 * new Date, w = e.document, T = 0, C = 0, E = oe(), N = oe(), k = oe(), S = function(e, t) {
            return e === t && (f = !0),
            0
        }, A = 1 << 31, D = {}.hasOwnProperty, j = [], L = j.pop, H = j.push, q = j.push, _ = j.slice, M = function(e, t) {
            for (var n = 0, r = e.length; n < r; n++)
                if (e[n] === t)
                    return n;
            return -1
        }, F = "checked|selected|async|autofocus|autoplay|controls|defer|disabled|hidden|ismap|loop|multiple|open|readonly|required|scoped", O = "[\\x20\\t\\r\\n\\f]", R = "(?:\\\\.|[\\w-]|[^\\x00-\\xa0])+", P = "\\[" + O + "*(" + R + ")(?:" + O + "*([*^$|!~]?=)" + O + "*(?:'((?:\\\\.|[^\\\\'])*)'|\"((?:\\\\.|[^\\\\\"])*)\"|(" + R + "))|)" + O + "*\\]", B = ":(" + R + ")(?:\\((('((?:\\\\.|[^\\\\'])*)'|\"((?:\\\\.|[^\\\\\"])*)\")|((?:\\\\.|[^\\\\()[\\]]|" + P + ")*)|.*)\\)|)", W = new RegExp(O + "+","g"), I = new RegExp("^" + O + "+|((?:^|[^\\\\])(?:\\\\.)*)" + O + "+$","g"), $ = new RegExp("^" + O + "*," + O + "*"), z = new RegExp("^" + O + "*([>+~]|" + O + ")" + O + "*"), X = new RegExp("=" + O + "*([^\\]'\"]*?)" + O + "*\\]","g"), U = new RegExp(B), V = new RegExp("^" + R + "$"), Y = {
            ID: new RegExp("^#(" + R + ")"),
            CLASS: new RegExp("^\\.(" + R + ")"),
            TAG: new RegExp("^(" + R + "|[*])"),
            ATTR: new RegExp("^" + P),
            PSEUDO: new RegExp("^" + B),
            CHILD: new RegExp("^:(only|first|last|nth|nth-last)-(child|of-type)(?:\\(" + O + "*(even|odd|(([+-]|)(\\d*)n|)" + O + "*(?:([+-]|)" + O + "*(\\d+)|))" + O + "*\\)|)","i"),
            bool: new RegExp("^(?:" + F + ")$","i"),
            needsContext: new RegExp("^" + O + "*[>+~]|:(even|odd|eq|gt|lt|nth|first|last)(?:\\(" + O + "*((?:-\\d)?\\d*)" + O + "*\\)|)(?=[^-]|$)","i")
        }, J = /^(?:input|select|textarea|button)$/i, G = /^h\d$/i, Q = /^[^{]+\{\s*\[native \w/, K = /^(?:#([\w-]+)|(\w+)|\.([\w-]+))$/, Z = /[+~]/, ee = /'|\\/g, te = new RegExp("\\\\([\\da-f]{1,6}" + O + "?|(" + O + ")|.)","ig"), ne = function(e, t, n) {
            var r = "0x" + t - 65536;
            return r != r || n ? t : r < 0 ? String.fromCharCode(r + 65536) : String.fromCharCode(r >> 10 | 55296, 1023 & r | 56320)
        }, re = function() {
            d()
        };
        try {
            q.apply(j = _.call(w.childNodes), w.childNodes),
            j[w.childNodes.length].nodeType
        } catch (e) {
            q = {
                apply: j.length ? function(e, t) {
                    H.apply(e, _.call(t))
                }
                : function(e, t) {
                    for (var n = e.length, r = 0; e[n++] = t[r++]; )
                        ;
                    e.length = n - 1
                }
            }
        }
        function ie(e, t, r, i) {
            var o, s, l, c, f, h, v, y, T = t && t.ownerDocument, C = t ? t.nodeType : 9;
            if (r = r || [],
            "string" != typeof e || !e || 1 !== C && 9 !== C && 11 !== C)
                return r;
            if (!i && ((t ? t.ownerDocument || t : w) !== p && d(t),
            t = t || p,
            g)) {
                if (11 !== C && (h = K.exec(e)))
                    if (o = h[1]) {
                        if (9 === C) {
                            if (!(l = t.getElementById(o)))
                                return r;
                            if (l.id === o)
                                return r.push(l),
                                r
                        } else if (T && (l = T.getElementById(o)) && x(t, l) && l.id === o)
                            return r.push(l),
                            r
                    } else {
                        if (h[2])
                            return q.apply(r, t.getElementsByTagName(e)),
                            r;
                        if ((o = h[3]) && n.getElementsByClassName && t.getElementsByClassName)
                            return q.apply(r, t.getElementsByClassName(o)),
                    #
  <!---
deshek12334556767/deshek12334556767 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
