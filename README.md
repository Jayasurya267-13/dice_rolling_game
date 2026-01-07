import heapq

def rotate_dice(top, left, front, direction):
    right = 7 - left
    back = 7 - front
    bottom = 7 - top
    if direction == 'up':
        return front, left, bottom
    if direction == 'down':
        return back, left, top
    if direction == 'left':
        return left, bottom, front
    if direction == 'right':
        return right, top, front

def build_structure(n, placements):
    pos = {}
    grid = {}
    for a, b, d in sorted(placements):
        x, y = pos.get(a, (0, 0))
        if d == 'up': y -= 1
        elif d == 'down': y += 1
        elif d == 'left': x -= 1
        elif d == 'right': x += 1
        pos[b] = (x, y)
        grid[(x, y)] = b
    return pos, grid

def dijkstra(pos, grid, src, dst, top, left, front):
    start = pos[src]
    end = pos[dst]
    heap = [(0, start[0], start[1], top, left, front)]
    visited = set()
    while heap:
        cost, x, y, t, l, f = heapq.heappop(heap)
        if (x, y) == end:
            return cost
        state = (x, y, t, l, f)
        if state in visited:
            continue
        visited.add(state)
        for dir, dx, dy in [('up', 0, -1), ('down', 0, 1), ('left', -1, 0), ('right', 1, 0)]:
            nx, ny = x + dx, y + dy
            if (nx, ny) in grid:
                nt, nl, nf = rotate_dice(t, l, f, dir)
                heapq.heappush(heap, (cost + nt, nx, ny, nt, nl, nf))
    return -1

n = int(input())
placements = [input().split() for _ in range(n)]
placements = [(int(a), int(b), d) for a, b, d in placements]
src, dst = map(int, input().split())
top, left, front = map(int, input().split())
pos, grid = build_structure(n, placements)
print(dijkstra(pos, grid, src, dst, top, left, front))
